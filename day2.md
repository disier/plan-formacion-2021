## Day 2: Set up a Static Web page with Azure Storage and custom domain HTTPS

These are the steps done:
1. Crear Azure Storage resource
2. Enable Web Access
3. Import code from Azure Storage Explorer
4. Create custom subdomain static.blaumark.es and point it to the storage
  `az storage account update --resource-group BlaumarkWebTest --name blamarkwebstorage --custom-domain static.blaumark.es --use-subdomain false`
6. Create Azure CDN with custom endpoint
7. Create a Let's Encrypt SSL certificate on an Ubuntu WSL instacne
  `sudo certbot certonly --cert-name static.blaumark.es --manual -d static.blaumark.es --preferred-challenges dns`
  `sudo openssl pkcs12 -export -inkey /etc/letsencrypt/live/static.blaumark.es/privkey.pem -in /etc/letsencrypt/live/static.blaumark.es/fullchain.pem -name static.blaumark.es -out static.blaumark.es.pfx`
9. Export the certificate as PFX file
10. Create a Azure Key Vault instance
11. Registry application
  `New-AzADServicePrincipal -ApplicationId "205478c0-bd83-4e1b-a9d6-db63a3e1e1c8"`
13. Create the certificate and give access to Azure CDN
14. Configurate Azure CDN custom domain with custom certificate
15. Modify DNS entry to point to Azure CDN endpoint
