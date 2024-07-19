# App  
    - registering routes (for resources and middleware)
    - stores application state (shared across all handlers within the same scope)
## Scope
    - namespace for all routes
    - HttpServer::new() -> App::new() -> services|-> scope -> routes
                                                 |->app_data(Data<T>)
#### Using an Application Scope to Compose Applications
     - web::scope() method allows setting a resource group prefix
## state Data<T>
   - state is shared with all routes and resources within the same scope
#### Shared Mutable State
   - State initialized inside HttpServer::new is local to the worker thread and may become de-synced if modified.
   - to make global initialize outside Httpserver::new
