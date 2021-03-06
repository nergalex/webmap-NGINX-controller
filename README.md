``` yaml
extra_app:
  gateways:
    - instance: nginxapigw
      location: azure-totalinbound
  client_id: ***********
  components:
    - name: MapServer
      type: api
      openapi_spec_uri: >-
        https://raw.githubusercontent.com/nergalex/webmap-NGINX-controller/master/swaggers/webmap_oas3.json
      version: v1.0.0
      workloads:
        - 'http://10.100.0.51'
      identityProviders:
        - dev-431905.okta.com
    - name: Arcadia_api
      type: api
      openapi_spec_uri: >-
        https://raw.githubusercontent.com/nergalex/webmap-NGINX-controller/master/swaggers/arcadia_oas3.json
      version: v1.0.0
      workloads:
        - 'http://10.12.1.5:80'
      identityProviders:
        - dev-431905.okta.com
    - name: Arcadia_main
      type: adc
      uri: /
      workloads:
        - 'http://10.12.1.5:81'
    - name: Arcadia_app2
      type: adc
      uri: /api/
      workloads:
        - 'http://10.12.1.5:82'
    - name: Arcadia_app3
      type: adc
      uri: /app3/
      workloads:
        - 'http://10.12.1.5:83'
    - name: Arcadia_db
      type: adc
      uri: /files/
      workloads:
        - 'http://10.12.1.5:84'
  domain: f5app.dev
  name: WebMap
extra_idp:
  dev-431905.okta.com:
    jwks_uri: 'https://***********.okta.com/oauth2/default/v1/keys'
extra_nginx_controller_environment: ***********
extra_nginx_controller_ip: 10.0.0.17
extra_nginx_controller_password: ***********
extra_nginx_controller_username: ***********
```