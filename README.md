# Multi-Tenant Login System Task Documentation

# 1. Setup

# Set up a new Django project with Django Tenant Schemas.

1.1 Create New Django Project:
   - Begin by executing `django-admin startproject project` in the terminal.
   - Move into the project directory using `cd project`.

1.2 Install Django Tenant Schemas:
   - Utilize `pip install django django-tenant-schemas` to install the necessary packages.

1.3 Create a Simple Model for Tenants (Client Model):
   - Generate a new app with `python manage.py startapp tenants`.
   - Define a basic model, like `Client`, in `tenants/models.py`.

1.4 Run Migrations:
   - Execute `python manage.py makemigrations` and `python manage.py migrate_schemas` to apply the model changes to the database.

# 2. Tenant Registration

# Implement a view or form for tenant registration.

2.1 Create Tenant Registration View:
   - Develop a view or form in `client_app/views.py` that handles tenant registration.
   - Ensure that a new tenant is created in the system when a user registers a new account.

2.2 Update URL Configuration:
   - Incorporate the registration view into `multi_tenant_project/urls.py`.

# 3. Custom User Model

# Create a custom user model that extends the default Django user model.

3.1 Update Settings:
   - Modify `multi_tenant_project/settings.py` to include the custom user model using `AUTH_USER_MODEL`.

3.2 Create Tenant-Aware Custom User Model:
   - Define the `CustomUser` model in `tenants/models.py` by extending the `AbstractUser` class.
   - Apply migrations using `python manage.py makemigrations` and `python manage.py migrate_schemas`.

# 4. Custom Login View

# Implement a custom login view.

4.1 Create Custom Login View:
   - Develop a custom login view in `tenants/views.py` that redirects users to their respective schema's webpage upon successful login.
   - Ensure the login view functions for both the public portal and tenant-specific subdomains.

4.2 Update URL Configuration:
   - Integrate the custom login view into `multi_tenant_project/urls.py`.

## 6. URL Configuration

### Configure URLs.

6.1 **Update URL Configuration:**
   - In `app and client_app /urls.py`, ensure that the URLs are structured correctly and follow best practices.
   - Include tenant-specific webpages and the custom login view.



# Dependencies:
Python: Ensure that Python is installed on your system. You can download it from python.org.

Django and Django Tenant Schemas: Install Django and Django Tenant Schemas using pip. Open a terminal or command prompt and run:
