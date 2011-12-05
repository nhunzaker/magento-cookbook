# Fixing the Upload Security Error

This problem is caused when the setting `Use Secure URLs in [frontend/admin]` has been set to "Yes". Fixing this issue is simple:

1. Visit `System » Configuration`
2. Select `Web » Secure`
3. In the field `Use Secure URLs in [frontend/admin]` set the value to "No"

## Notes:

This is no substitute for having a secure connection in a production environment.
