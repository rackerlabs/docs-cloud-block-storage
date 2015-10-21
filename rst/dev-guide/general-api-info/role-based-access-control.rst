.. _role-based-access-control:

Role Based Access Control
-------------------------

Role Based Access Control (RBAC) restricts access to the capabilities of
Rackspace Cloud services, including the Cloud Block Storage API, to
authorized users only. RBAC enables Rackspace Cloud customers to specify
which account users of their Cloud account have access to which Cloud
Block Storage API service capabilities, based on roles defined by Rackspace (see Roles available for Cloud Block Storage below). The permissions to perform certain operations in Cloud Block Storage
API – create, read, update, delete – are assigned to specific roles. The account owner user assigns these roles, either product-specific or global (multiproduct), to account users.

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

*  :rax-devdocs:`Add user<cloud-identity/v2/developer-guide/#post-add-user-v2-0-users>`

*  :rax-devdocs:`Add role to user <cloud-identity/v2/developer-guide/#add-role-to-user-v2-0-os-ksadm>`

*  :rax-devdocs:`Delete global role from user <cloud-identity/v2/developer-guide/#delete-global-role-from-user-v2-0-os-ksadm>`

.. note::
   The account admin user (identity:user-admin) role cannot hold any
   additional roles because it already has full access to all capabilities
   by default.

.. _cbs-dg-rbac-available:

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
please review the :kc-article:`Permissions Matrix for Role-Based Access Control<permissions-matrix-for-role-based-access-control-rbac>`.

