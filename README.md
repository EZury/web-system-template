# Yes No API
- [x] Replace "WEB system" with your system name

## Description
- [x] Provide WEB system description in few sentences - its purpose, users, etc.

    Yes No API works like this: you provide answer (only from these: "yes", "no" and "maybe") based on this I get random gif with that type of answer (Example: if I want to get gif which will imply an answer yes, I have to provide GET post with "answer" : "yes"). Because of this I don't have that many choices to make interesting site. My solution is to create different script who will get all objects or atleast significant amount of objects for me to play with. When I have all those objects then I can modify them to my liking, uses I like to achieve:
    - Add "time" when that object was created (on my server) and time when that object was modified, how many "likes" and "views" that object has (for list purposes) and ID.
    - Web System will provide list of images with with different answers, then I can provide Most popular lists, Most viewed lists.
    - Web System will provide a few buttons to add Image and get Random Image.

## Entity definition
- [x] Define the entity ("object" that will be manipulated) of WEB system

    imageEntity = {
        "id" : (number 20),
        "creationDate" : (date),
        "modificationDate" : (date),
        "likes" : (number 10),
        "views" : (number 10),
        "answer" : (string 10),
        "forced" : (string 10),
        "image" : (string 100 (URL))
    };
    
    date ISO 8601 format = yyyy-mm-ddThh:mm:ss.ffffff
    
- [x] Entity should have a name
- [x] Entity should have 3 mandatory attributes:
    - [x] ID - depending on specific service this could be a number or string
    - [x] Creation date - (if applicable for specific service) ISO 8601 format date string
    - [x] Modification date - (if applicable for specific service) ISO 8601 format date string
- [x] Entity should have at least 5 custom attributes
    - [x] Each attribute should have a type defined: number, string, ISO 8601 date string, boolean, object, array or other
    - [x] Each attribute should have restrictions defined: list of constants, or number range, or string length, or string format, or object schema, or array schema or other. For example, you can use `joi` language to define restrictions: https://github.com/hapijs/joi/blob/v13.1.2/API.md

## API definition
- [x] Define specific service (konkrečios paslaugos) API methods that WEB system is going to use
    GET /api    - returns random GIF entity from https://yesno.wtf/#api.
- [x] Optionally define additional API methods that WEB system is going to expose
- [x] API should have at least 4 methods
    - [x] A method to return entity by ID. Should not have request body
    
        GET /api/image/{id}             - returns image entity by it's id.
        
        POST errors:
        400 - Bloga užklausa.
        404 - Nerastas Entity.
        
    - [x] A method to return multiple entities (Array) by ID. This method should support at least one header value to:
    
        GET /api/images/{string}         - returns images by {string} condition.
        
        POST errors:
        400 - Bloga užklausa.
        404 - Nerasti Entity.
        
    - [x] A method to remove entity by ID. Returns removed entity. Should not have request body
    
        DELETE /api/image/{id}          - deletes image entity by it's id.
        
        POST errors:
        400 - Bloga užklausa.
        401 - Neturi prieigos.
    
    - [x] A method to update entity by ID. Accepts entity to update and returns updated entity
    
        POST /api/image/{id}            - updates/creates image entity by it's id.
        
        POST errors:
        400 - Bloga užklausa.
        401 - Neturi prieigos.
    
- [x] Each method should have HTTP method defined
- [x] Each method should have URI defined (use {id} as entity ID placeholder)
- [x] Should return all 4xx errors in unified format. Define format using `joi` language
- [x] Should return all 5xx errors in unified format. Define format using `joi` language
        
        500 - Serveris neprieinamas.

## UI definition

    https://wireframe.cc/pro/edit/240753

- [x] Define the structure of how visually the WEB system is going to look like
- [x] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [x] The view should have a title
- [x] The view should have a description of a service provided by web system
- [x] The view should include at least 2 UI components:
    - [x] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
    - [x] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity
