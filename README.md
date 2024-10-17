import cv2

# Carregar um classificador pré-treinado para carros
car_cascade = cv2.CascadeClassifier('cars.xml')

# Carregar uma imagem
img = cv2.imread('imagem_com_carro_e_pessoa.jpg')

# Converter para escala de cinza
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

# Detectar carros
cars = car_cascade.detectMultiScale(gray, 1.1, 4)

# Desenhar retângulos em torno dos carros detectados
for (x,y,w,h) in cars:
    cv2.rectangle(img,(x,y),(x+w,y+h),(0,255,0),2)

# Mostrar a imagem com os carros detectados
cv2.imshow('Carros Detectados', img)
cv2.waitKey(0)
