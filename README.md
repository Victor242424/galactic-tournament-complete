# Torneo Galáctico

Sistema de gestión del Gran Torneo Galáctico - Un enfrentamiento entre las especies más poderosas del universo que ocurre cada 500 años.

## Descripción

Aplicación Full Stack que permite:
- Registrar especies con nombre, nivel de poder y habilidad especial
- Realizar combates entre especies (manual y aleatorio)
- Visualizar ranking de especies por victorias
- Consultar historial completo de combates

### Reglas de Combate
1. Gana la especie con mayor **nivel de poder**
2. En caso de empate, gana la especie con nombre **alfabéticamente primero**

## Stack Tecnológico

### Backend
- **Java 17**
- **Spring Boot 3.2.0**
- **Spring Data JPA**
- **H2 Database** (en memoria)
- **Maven**
- **Lombok**

### Frontend
- **HTML5**
- **Tailwind CSS 3**
- **JavaScript (Vanilla)**

## Requisitos Previos

### Ejecución Local
- Java 17 o superior
- Maven 3.6+
- H2 Database
- Navegador web moderno

## Instalación y Ejecución

#### 1. Clonar el repositorio
```bash
git clone git@github.com:Victor242424/galactic-tournament-complete.git
cd galactic-tournament-complete
```

#### 2. Compilar y ejecutar el backend
```bash
# Compilar el proyecto
mvn clean package

# Ejecutar la aplicación
mvn spring-boot:run

El backend estará disponible en: `http://localhost:8080`

#### 3. Abrir el frontend
Abrir directamente el archivo index.html en el navegador

## Ejecutar Tests

```bash
# Ejecutar todos los tests
mvn test
```

## API Endpoints

### Especies

#### Registrar nueva especie
```http
POST /api/especies
Content-Type: application/json

{
  "nombre": "Kryptoniano",
  "nivelPoder": 9500,
  "habilidadEspecial": "Superfuerza y vuelo"
}
```

#### Listar todas las especies
```http
GET /api/especies
```

#### Obtener especie por ID
```http
GET /api/especies/{id}
```

### Combates

#### Iniciar combate manual
```http
POST /api/combates
Content-Type: application/json

{
  "especie1Id": 1,
  "especie2Id": 2
}
```

#### Iniciar combate aleatorio
```http
POST /api/combates/aleatorio
```

#### Listar historial de combates
```http
GET /api/combates
```

### Ranking

#### Obtener ranking
```http
GET /api/ranking
```

## Uso de la Interfaz Web

### 1. Registrar Especies
- Navega a la pestaña **"Especies"**
- Completa el formulario con:
  - Nombre de la especie
  - Nivel de poder (número entero positivo)
  - Habilidad especial (descripción)
- Haz clic en **"Registrar Especie"**

### 2. Realizar Combates
- Navega a la pestaña **"Combate"**
- **Opción A - Combate Manual:**
  - Selecciona dos especies diferentes
  - Haz clic en **"Iniciar Combate"**
- **Opción B - Combate Aleatorio:**
  - Haz clic en **"Combate Aleatorio"**
  - El sistema seleccionará dos especies aleatoriamente

### 3. Ver Ranking
- Navega a la pestaña **"Ranking"**
- Visualiza la tabla con:
  - Posición en el ranking
  - Estadísticas de victorias y derrotas
  - Nivel de poder y habilidades

### 4. Consultar Historial
- Navega a la pestaña **"Historial"**
- Revisa todos los combates realizados con:
  - Combatientes
  - Ganador
  - Resultado detallado
  - Fecha y hora del combate

## Arquitectura

### Backend (Arquitectura en Capas)

```
Controller (API REST)
    ↓
Service (Lógica de Negocio)
    ↓
Repository (Acceso a Datos)
    ↓
Database (H2 en memoria)
```

## Autor

Desarrollado como prueba técnica para demostrar habilidades en:
- Desarrollo Full Stack
- Java y Spring Boot
- Diseño de APIs REST
- Frontend moderno
- Testing y buenas prácticas

