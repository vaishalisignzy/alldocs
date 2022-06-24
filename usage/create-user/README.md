# Create User

### Steps to create a user :&#x20;

The API is used for creating a new user for binding data and displaying accordingly on backops portal or when downloading data

Creating the user is a simple two-step process:- \
**Step1**:- **** You first need to hit the backops user login with valid credentials which will return an access token which is needed to be passed in the user creation request\
**Step2**:- **** Second you need to make a create request with basic user details which returns **merchantId**\
that will be needed in further requests

{% content-ref url="step1-backops-user-login.md" %}
[step1-backops-user-login.md](step1-backops-user-login.md)
{% endcontent-ref %}

{% content-ref url="step2-create-request.md" %}
[step2-create-request.md](step2-create-request.md)
{% endcontent-ref %}



