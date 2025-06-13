# PROCESS
# Simple Image Processor

Pacote Python para processamento simples de imagens utilizando a biblioteca Pillow (PIL).

## Funcionalidades

- Redimensionar imagens
- Converter para escala de cinza
- Rotacionar imagens
- Salvar imagens processadas

## Instalação

Clone este repositório e instale as dependências:

```bash
git clone https://github.com/seu-usuario/simple-image-processor.git
cd simple-image-processor
pip install -r requirements.txt

from simple_image_processor import SimpleImageProcessor

processor = SimpleImageProcessor("entrada.jpg")
processor.resize(200, 200).to_grayscale().rotate(90).save("saida.jpg")


Substitua `seu-usuario` pelo seu nome de usuário no GitHub.

---



### `simple_image_processor/__init__.py`

```python
from .processor import SimpleImageProcessor

from PIL import Image
import os

class SimpleImageProcessor:
    def __init__(self, image_path):
        if not os.path.exists(image_path):
            raise FileNotFoundError(f"Imagem não encontrada: {image_path}")
        self.image = Image.open(image_path)
        self.original_path = image_path

    def resize(self, width, height):
        self.image = self.image.resize((width, height))
        return self

    def to_grayscale(self):
        self.image = self.image.convert("L")
        return self

    def rotate(self, angle):
        self.image = self.image.rotate(angle)
        return self

    def save(self, output_path):
        self.image.save(output_path)
        return output_path
Pillow
MIT License

Copyright (c) 2025 Seu Nome

Permite-se que qualquer pessoa obtenha uma cópia deste software e arquivos de documentação associados, para lidar com o software sem restrições, incluindo sem limitação os direitos de usar, copiar, modificar, mesclar, publicar, distribuir, sublicenciar e/ou vender cópias do software, e para permitir que as pessoas a quem o software é fornecido o façam, sujeito às seguintes condições:

A cópia do aviso de direitos autorais e esta permissão devem ser incluídas em todas as cópias ou partes substanciais do software.

O software é fornecido "no estado em que se encontra", sem garantia de qualquer tipo, expressa ou implícita, incluindo, mas não se limitando às garantias de comercialização, adequação a um propósito específico e não infração. Em nenhum caso os autores ou detentores dos direitos autorais serão responsáveis por qualquer reclamação, dano ou outra responsabilidade, seja em uma ação de contrato, ato ilícito ou de outra forma, decorrente de, fora de ou em conexão com o software ou o uso ou outros negócios no software.
