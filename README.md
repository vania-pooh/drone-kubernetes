# Drone Server

This repository contains [Helm](http://github.com/kubernetes/helm) chart for installing [Drone](http://github.com/drone/drone) to Google Container Engine. Is was tested with Drone 0.8.0 which is using GRPC instead of WebSockets.

## Usage

1. Launch Kubernetes cluster and create a dedicated GCE storage disk for SQLite database.
2. Create Github OAuth application and get client and secret values.
3. Clone this repository and edit `values.yaml` - fill Github credentials and GCE storage disk name.
4. Go to parent directory and install chart with Helm: `$ helm install ./drone-kubernetes`.

## Further Improvements

Because of file-based database this chart runs only one Drone server replica. This can be changed by replacing SQLite with replicated relational database such as MySQL and PostgreSQL. 
