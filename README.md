# Python Development Plugin for `docker-dev`

This plugin makes it easy to use Docker while developing your Python projects.

In development, it's quite likely that you want to achieve the following:

- Install your Python distribution in editable mode (e.g., `pip install -e .`).
- Mount your distribution as read-only on the container, so that you get
  instant code reload.

However, those two things conflict, as the container can't write to the
read-only file system. You could drop this constraint and allow the container
to write to the directory, but this `.egg-info` directory wouldn't be owned
by you, which will lead to other problems.

This plugin is a workaround to this issue: It generates the `.egg-info` in the
host system, even before the image is built.

To learn more, read about [docker-dev](https://github.com/2degrees/docker-dev).
