=========================
Role Based Access Control
=========================

Role Based Access Control (RBAC) restricts access to the capabilities of
Rackspace Cloud services, including the Cloud Block Storage API, to
authorized users only. RBAC enables Rackspace Cloud customers to specify
which account users of their Cloud account have access to which Cloud
Block Storage API service capabilities, based on roles defined by
Rackspace. The permissions to perform certain operations in Cloud Block Storage
API – create, read, update, delete – are assigned to specific roles, and these
roles can be assigned by the Cloud account admin user to account users
of the account.

Assigning roles to account users
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The account owner (identity:user-admin) can create account users on the
account and then assign roles to those users. The roles grant the
account users specific permissions for accessing the capabilities of the
Cloud Block Storage service. Each account has only one account owner,
and that role is assigned by default to any Rackspace Cloud account when
the account is created.

See the *Cloud Identity Client Developer Guide* for information about
how to perform the following tasks:

*  `Create account
   users <http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/POST_addUser_v2.0_users_User_Calls.html>`__

*  `Assign roles to account
   users <http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/PUT_addUserRole__v2.0_users__userId__roles__roleid__Role_Calls.html>`__

*  `Delete roles from account
   users <http://docs.rackspace.com/auth/api/v2.0/auth-client-devguide/content/DELETE_deleteUserRole__v2.0_users__userId__roles__roleid__Role_Calls.html>`__

.. note::
   The account admin user (identity:user-admin) role cannot hold any
   additional roles because it already has full access to all capabilities
   by default.

Roles available for Cloud Block Storage
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Three roles (admin, creator, and observer) can be used to access the
Cloud Block Storage API specifically. The following table describes
these roles and their permissions.

**Table: Cloud Block Storage product roles and capabilities**

+--------------+--------------------------------------------------------------+
| Role name    | Role permissions                                             |
+==============+==============================================================+
| cbs:admin    | This role provides Create, Read, Update, and Delete          |
|              | permissions in Cloud Block Storage, where access is granted. |
+--------------+--------------------------------------------------------------+
| cbs:creator  | This role provides Create, Read and Update permissions in    |
|              | Cloud Block Storage, where access is granted.                |
+--------------+--------------------------------------------------------------+
| cbs:observer | This role provides Read permission in Cloud Block Storage,   |
|              | where access is granted.                                     |
+--------------+--------------------------------------------------------------+

Additionally, two multiproduct roles apply to all products. Users with
multiproduct roles inherit access to future products when those products
become RBAC-enabled. The following table describes these roles and their
permissions.

**Table: Multiproduct (global) roles and permissions**

+-----------+-----------------------------------------------------------------+
| Role name | Role permissions                                                |
+-----------+-----------------------------------------------------------------+
| admin     | This role provides Create, Read, Update, and Delete permissions |
|           | in all products, where access is granted.                       |
+-----------+-----------------------------------------------------------------+
| observer  | This role provides Read permission in all products, where access|
|           | is granted.                                                     |
+-----------+-----------------------------------------------------------------+

Resolving conflicts between RBAC multiproduct vs. custom (product-specific) roles
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The account owner can set roles for both multiproduct and Cloud Block
Storage scope, and it is important to understand how any potential
conflicts among these roles are resolved. When two roles appear to
conflict, the role that provides the more extensive permissions takes
precedence. Therefore, admin roles take precedence over observer and
creator roles, because admin roles provide more permissions.

The following shows two examples of how potential conflicts
between user roles in the Control Panel are resolved.

+--------------------------------+-----------------------+------------------------------------+
| Permission configuration       | View of permission    | Can the user perform product admin |
|                                | in the control panel  | functions in the Control Panel?    |
+================================+=======================+====================================+
| User is assigned the following | Appears that the user | Yes, for Cloud Block Storage only. |
| roles: multiproduct observer   | has only the          | The user has the observer role for |
| and Cloud Block Storage admin  | multiproduct observer | the rest of the products.          |
|                                | role                  |                                    |
+--------------------------------+-----------------------+------------------------------------+
| User is assigned the following | Appears that the user | Yes, for all of the products.      |
| roles: multiproduct admin and  | has only the          | The Cloud Block Storage observer   | 
| Cloud Block Storage observer   | multiproduct admin    | is ignored.                        |
|                                | role                  |                                    |
+--------------------------------+-----------------------+------------------------------------+

RBAC permissions cross-reference to Cloud Block Storage API operations
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

API operations for Cloud Block Storage may or may not be available to
all roles. To see which operations are permitted to invoke which calls,
please review the `Knowledge Center
article <http://www.rackspace.com/knowledge_center/article/permissions-matrix-for-role-based-access-control-rbac>`_.

