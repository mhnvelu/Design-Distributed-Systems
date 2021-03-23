# Single Node Patterns

Why you might also want to break up the components running on
a single machine into different containers?

```
    * The goal of a container is to establish boundaries around specific resources
(e.g., this application needs two cores and 8 GB of memory).

    * The boundary
delineates team ownership (e.g., this team owns this image).

    * The boundary is
intended to provide separation of concerns (e.g., this image does this one thing) ensures that your application is well understood
and can easily be tested, updated, and deployed. Small, focused applications are
easier to understand and have fewer couplings to other systems.

All of these reasons provide motivation for splitting up an application on a single
machine into a group of containers.
```

- All of Single Node patterns
  assume tight dependencies among all of the containers.
- All of the containers in the pattern can be reliably coscheduled onto a single machine.
- They also assume that all of the containers in the pattern can
  optionally share volumes or parts of their filesystems as well as other key container
  resources like network namespaces and shared memory. This tight grouping is called
  a pod in Kubernetes.

Single Node Patterns are listed below:

- [Sidecar](side-car/README.md)
- [Ambassador](ambassadors/README.md)
