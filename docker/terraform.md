# Terraform in Docker betreiben 

## Basics 

  * Terraform bietet ein image in dem immer die neueste terraform - cli drin ist.
  * https://hub.docker.com/r/hashicorp/terraform/

## Nachteile 

  * Das image startet immer direkt als entrypoint terraform
  * Sprich: Es wird beim Starten direkt Terraform ausgeführt.

## Fix und warum ? 

  * Ich möchte Projekte in git verwalten, d.h. die ganzen Configs / Rezepte für terraform
  * Diese will Dein automatisch reinclonen und mit terraform verwenden.
  * Dazu soll der Container direkt mit sh statt terraform starten:

```
# There we have it
docker run -it --entrypoint '' hashicorp/terraform sh
```

