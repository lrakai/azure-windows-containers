# You are extending the `microsoft/aspnet` image.

FROM microsoft/aspnet

# The final instruction copies a published into the container.

COPY ./PublishOutput/ /inetpub/wwwroot

# No CMD or ENTRYPOINT needed since the base image declares 
# the IIS process as the default