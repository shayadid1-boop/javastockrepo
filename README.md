# Iditex

A Java web application for a Java course, built as a Google App Engine (GAE) project in Eclipse.

The app serves a simple welcome page and a servlet that prints the result of a basic arithmetic exercise.

## Features

- Welcome page at `/` (`war/index.html`)
- Servlet at `/iditex` that evaluates `(4 + 3) * 7` and returns the result as HTML
- Configured for Google App Engine Java (SDK 1.9.17) with JPA / DataNucleus persistence settings

## Project structure

```
src/
  com/myorg/javacourse/IditexServlet.java   # HTTP servlet
  META-INF/persistence.xml                 # JPA persistence unit
  META-INF/jdoconfig.xml                   # JDO configuration
  log4j.properties
war/
  index.html                               # Welcome page
  WEB-INF/
    web.xml                                # Servlet mapping
    appengine-web.xml                      # App Engine application config
    logging.properties
```

## Requirements

- Java (compatible with the Eclipse JRE used by the project)
- [Google Plugin for Eclipse](https://developers.google.com/eclipse/) and Google App Engine Java SDK **1.9.17**
- Eclipse with the Google App Engine project nature (this repository is an Eclipse GAE web app)

## Running locally

1. Import the project into Eclipse as an existing project (`iditex`).
2. Ensure the Google App Engine SDK container is on the classpath.
3. Run as a **Web Application** (Google App Engine local development server).
4. Open the welcome page in a browser (typically `http://localhost:8888/`).

## Endpoints

| Path     | Description                                      |
|----------|--------------------------------------------------|
| `/`      | Welcome page with a link to the math exercise    |
| `/iditex`| `IditexServlet` — prints `(4+3)*7=49` as HTML    |

## App Engine configuration

- Application ID: `javaiditwein`
- Version: `2`
- Thread-safe: enabled
- Servlet mapping: `com.myorg.javacourse.IditexServlet` → `/iditex`

To deploy, use the Google Plugin for Eclipse **Deploy to App Engine** action, or the App Engine SDK `appcfg` tool against the `war/` directory.

## License

This project is provided for educational use as part of a Java course.
