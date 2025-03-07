# Olla Academy Digital Library

Welcome to the Olla Academy Digital Library project! This initiative aims to provide accessible and engaging educational resources to children, especially those in underserved communities.

## About Olla Academy

Olla Academy is dedicated to bridging the educational gap by offering a user-friendly and scalable digital library. Our platform provides a diverse collection of digital books, learning materials, and interactive content. By focusing on accessibility, we strive to ensure that every child has the opportunity to learn and grow.

## Project Goals

* **Accessibility:** Provide high-quality educational resources to children, regardless of their location or internet connectivity.
* **Offline Functionality:** Enable continuous learning in low-connectivity areas through offline access.
* **Community Collaboration:** Foster an open-source environment where educators, institutions, and developers can contribute and improve the platform.
* **Scalability:** Build a robust and scalable system that can accommodate a growing library and user base.
* **Engaging Content:** Curate and create interactive and engaging content that sparks curiosity and fosters a love for learning.

## Features

* Wide range of digital books and educational materials.
* User-friendly interface designed for children.
* Online and (soon) offline access.
* Interactive learning content.
* Open-source platform for community contributions.

## Technology

This project builds upon the foundation of a robust and well-regarded project called Kavita, providing a solid base for Olla Academy's initial goals.

## Installation

The Olla Academy Digital Library can be easily deployed using Docker. Here's a quick guide to get you started:

**Prerequisites:**

* Docker and Docker Compose installed on your system.

**Using Docker Compose (Recommended):**

1.  **Create a `docker-compose.yml` file:**

    ```yaml
    version: "3.8"
    services:
      olla-library:
        image: fabricverse/library:latest # Or your forked image.
        container_name: olla-library
        ports:
          - "5000:5000"
        volumes:
          - /your/library/content:/library # Replace with your library content directory
          - /your/config/directory:/library/config # Replace with your configuration directory
        environment:
          - TZ=Your/Timezone # Replace with your timezone (e.g., Africa/Lusaka)
          - DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=true
        restart: unless-stopped
    ```

    **Understanding Docker Compose Volumes:**

    * The key to configuring your library is understanding Docker volumes. In the `volumes` section, the syntax is `host_path:container_path`.
    * `/your/library/content:/library` means the directory on your computer (`/your/library/content`) containing your digital books and learning materials will be accessible inside the container at `/library`.
    * `/your/config/directory:/library/config` maps your configuration folder. Ensure the configuration folder has proper read write permissions.
    * **Important:** Replace `/your/library/content` and `/your/config/directory` with the actual paths on your host machine.

2.  **Start the container:**

    ```bash
    docker-compose up -d
    ```

3.  **Access the library:**

    * Open your web browser and navigate to `http://localhost:5000`.


## Contributing

We welcome contributions from the community! Whether you're a developer, educator, or content creator, your expertise can help us improve the Olla Academy Digital Library.

To contribute:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Submit a pull request.

## Future Development

We are continually working to improve the Olla Academy Digital Library. Future development plans include:

* Enhanced offline functionality.
* Expanded content library.
* Improved user interface and experience.
* Integration of more interactive learning tools.
* Improved search and filtering.

## Acknowledgements

This project leverages concepts and structures found in existing open source library management projects.

## License

This project is licensed under the GPL3 License.
