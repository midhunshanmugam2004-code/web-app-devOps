# Go Web App DevOps

A simple Go web application that serves static HTML pages and is designed as a lightweight example for DevOps workflows, containerization, Kubernetes deployment, and GitOps automation.

The app exposes a few pages such as Home, Courses, About, and Contact, and it is packaged for local, Docker, and Kubernetes-based deployments.

## Features

- Go-based HTTP server using the standard library
- Static HTML pages stored in the `static/` directory
- Docker image support
- Kubernetes manifests for deployment and service exposure
- Helm chart for package-based deployment
- EKS, ingress, and ArgoCD setup examples for cloud deployment workflows

## Project structure

```text
.
├── .github/workflows/      # CI/CD workflow examples
├── eks/                    # EKS setup notes and installation docs
├── gitops/                 # GitOps / ArgoCD documentation
├── helm/                   # Helm chart for the application
├── ingress-controller/     # Ingress controller installation docs
├── k8s/                    # Kubernetes manifests
├── static/                 # Website pages and assets
├── Dockerfile              # Container build definition
├── go.mod                  # Go module definition
├── main.go                 # Application entrypoint
├── main_test.go            # Basic Go tests
├── LICENSE                 # Project license
└── README.md               # Project documentation
```

## Routes

The server listens on port `8080` and serves:

- `/home`
- `/courses`
- `/about`
- `/contact`

Example:

```bash
http://localhost:8080/courses
```

## Local development

From the project root, run:

```bash
go run main.go
```

Then open the app in a browser:

```text
http://localhost:8080/home
```

## Docker

Build the image:

```bash
docker build -t go-web-app .
```

Run the container:

```bash
docker run -p 8080:8080 go-web-app
```

The app will be available at:

```text
http://localhost:8080
```

## Kubernetes

Apply the provided manifests:

```bash
kubectl apply -f k8s/manifests/
```

This includes a Deployment and Service for the application.

## Helm deployment

Install the Helm chart:

```bash
helm install go-web-app ./helm/go-web-app-chart
```

You can customize values in:

```text
helm/go-web-app-chart/values.yaml
```

## EKS and GitOps setup

This repo also includes examples for:

- Amazon EKS provisioning and configuration in `eks/`
- NGINX ingress setup in `ingress-controller/`
- ArgoCD / GitOps configuration in `gitops/`

## Application preview

![Website](static/images/golang-website.png)

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.


