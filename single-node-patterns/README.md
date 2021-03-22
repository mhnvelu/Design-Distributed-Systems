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

## The Sidecar Pattern

The sidecar pattern is a singlenode
pattern made up of two containers. The first is the **application container**. It contains
the core logic for the application. Without this container, the application would
not exist. In addition to the application container, there is a **sidecar container**.

The role
of the sidecar is to augment and improve the application container, often **without the
application container’s knowledge**.

In its simplest form, a sidecar container can be
used to add functionality to a container that might otherwise be difficult to improve.
Sidecar containers are **coscheduled** onto the same machine via an atomic container
group, such as the pod API object in Kubernetes.

In addition to being scheduled on
the same machine, the application container and sidecar container **share a number of
resources, including parts of the filesystem, hostname and network, and many other
namespaces**.

### Adding HTTPS to a Legacy Service

![HTTPS Sidecar](Sidecar-HTTPS.JPG)
