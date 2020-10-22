# Ingress

【问题01】有时我们的需求是多个域名指向同个后端服务，那ingress-nginx该怎么配置。
```yaml
spec:
  rules:
  - host: foobar.com
    http: &http_rules
      paths:
      - backend:
          serviceName: foobar
          servicePort: 80
  - host: api.foobar.com
    http: *http_rules
  - host: admin.foobar.com
    http: *http_rules
  - host: status.foobar.com
    http: *http_rules
    
   ```
