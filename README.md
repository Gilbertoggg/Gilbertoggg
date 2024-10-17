import cv2
import tensorflow as tf

# Carregar um modelo pré-treinado (por exemplo, MobileNetV2)
model = tf.keras.applications.MobileNetV2(weights='imagenet')

# Carregar a imagem e pré-processá-la para o modelo
img = cv2.imread('imagem_com_sombras.jpg')
img = cv2.resize(img, (224, 224))  # Tamanho de entrada esperado pelo modelo
img_tensor = tf.keras.preprocessing.image.img_to_array(img)
img_tensor /= 255.

# Fazer a predição
predictions = model.predict(img_tensor[np.newaxis, ...])
predicted_class = np.argmax(predictions[0])

# Obter o nome da classe prevista (assumindo que você tem um mapeamento de classes)
class_names = ['árvore', 'portal', 'casa', ...]
print("A imagem contém:", class_names[predicted_class])
