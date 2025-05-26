# 🎮 Primeiro Script com Godot

Este projeto é baseado na documentação oficial da Godot, onde aprendemos a criar um script básico para dar controle ao jogador usando o `GDScript`.

## 🧠 O que foi aprendido

Durante este exercício, os principais conceitos aprendidos foram:

- Como conectar um script a um node (`Sprite2D`).
- Como controlar a **rotação** do jogador com as setas esquerda e direita.
- Como mover o jogador **para frente** ao pressionar a seta para cima.
- Diferença entre `Input` e `_unhandled_input()` para lidar com entrada do jogador.
- Utilização do `Input` singleton para verificar ações a cada quadro.
- Conceito de vetores com `Vector2.UP` e `Vector2.ZERO`.
- Multiplicação por `delta` para garantir movimento suave e independente do FPS.

## 🧩 Código Final

```gdscript
extends Sprite2D

var speed = 400
var angular_speed = PI

func _process(delta):
	var direction = 0
	if Input.is_action_pressed("ui_left"):
		direction = -1
	if Input.is_action_pressed("ui_right"):
		direction = 1

	rotation += angular_speed * direction * delta

	var velocity = Vector2.ZERO
	if Input.is_action_pressed("ui_up"):
		velocity = Vector2.UP.rotated(rotation) * speed

	position += velocity * delta
```
## 🕹️ Controles

* ◀️ Seta Esquerda: Gira o ícone para a esquerda.

* ▶️ Seta Direita: Gira o ícone para a direita.

* 🔼 Seta Cima: Move o ícone para frente na direção da rotação.
