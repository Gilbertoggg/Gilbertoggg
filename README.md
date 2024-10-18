import matplotlib.pyplot as plt

# ... (código anterior)

# Visualizar a imagem e a predição
plt.imshow(img)
plt.title(f"Predição: {class_names[predicted_class]}")
plt.axis('off')
plt.show()
