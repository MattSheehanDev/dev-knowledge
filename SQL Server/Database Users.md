Database Users
========================

1. Query DB Users
```
-- Principal types
-- A = Application role
-- C = User mapped to a certificate
-- E = External user from Azure Active Directory
-- G = Windows group
-- K = User mapped to an asymmetric key
-- R = Database role
-- S = SQL user
-- U = Windows user
-- X = External group from Azure Active Directory group or applications

select
    name as username,
    create_date,
    modify_date,
    type_desc as type,
    authentication_type_desc as authentication_type
from sys.database_principals
where
    type not in ('A', 'G', 'R', 'X')
    and sid is not null
    and name != 'guest'
order by username;
```

2.  Query list of Roles and Users
```
SELECT DP1.name AS DatabaseRoleName,   
   isnull (DP2.name, 'No members') AS DatabaseUserName   
 FROM sys.database_role_members AS DRM  
 RIGHT OUTER JOIN sys.database_principals AS DP1  
   ON DRM.role_principal_id = DP1.principal_id  
 LEFT OUTER JOIN sys.database_principals AS DP2  
   ON DRM.member_principal_id = DP2.principal_id  
WHERE DP1.type = 'R'
ORDER BY DP1.name;
```

3. Change Contained DB User password
```
ALTER USER [user_name] WITH PASSWORD = 'new_password_str'
```
