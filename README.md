``` yaml
extra_app:
  components:
    - name: MapServer
      openapi_spec_uri: 'https://raw.githubusercontent.com/nergalex/WebMap/master/apispec_1.json'
      version: v1.0.0
      workloads:
        - 'http://10.100.0.51'
      identityProviders:
        - dev-*******.okta.com
  domain: f5app.dev
  name: WebMap
extra_idp:
  - name: dev-*******.okta.com
    jwks_uri: 'https://dev-431905.okta.com/oauth2/default/v1/keys'
extra_nginx_controller_environment: POC
extra_nginx_controller_ip: 10.0.0.16
extra_nginx_controller_password: *******
extra_nginx_controller_username: *******
extra_vmss_name: nginxapigw

```