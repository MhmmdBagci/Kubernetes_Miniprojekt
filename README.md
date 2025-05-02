# Kubernetes_Miniprojekt


Willkommen!  
Dies ist mein Miniprojekt aus meinem Devops-Engeneer Kurs vom Meilenstein Kubernetes. 
Ich habe hier eine einfache statische Webseite (die von Chocolux) in einem Container mit **nginx** verpackt und dann in Kubernetes über ein Deployment und einen NodePort-Service veröffentlicht.  
Zusätzlich habe ich den **Metrics Server** eingerichtet, damit das System CPU-Auslastung messen kann – und damit automatisch neue Pods starten kann (Autoscaling mit HPA).


Buildhinweise:
1. Docker Image bauen
    docker build -t chocolux-webseite .
2. Deployment starten 
    kubctl apply -f deployment
3. Zugriff/Verbindung erstellenb
    http://localhost:30080
4. Skalierung testen
    watch kubectl get hpa,pods
5. Last erzeugen
    while true; do curl http://localhost:30080; done

