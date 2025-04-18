# 📝 Blog Post API Documentation

## Overview

This Django REST Framework project provides a simple blogging API to manage blog posts. It supports full CRUD operations: **Create**, **Read**, **Update**, **Delete**, and includes filtering posts by title.

---

## 🛠️ Technologies Used

- **Django**
- **Django REST Framework (DRF)**
- **SQLite** (default development database)

---

## 📦 Model

### `BlogPost`

| Field           | Type           | Description                        |
|----------------|----------------|------------------------------------|
| `id`            | `AutoField`    | Primary key (auto-generated)       |
| `title`         | `CharField`    | Title of the blog post (max 100)   |
| `content`       | `TextField`    | Main content of the blog post      |
| `published_date`| `DateTimeField`| Timestamp of creation (auto-added) |

---

## 🔄 Serializer

### `BlogPostSerializer`

Serializes and deserializes `BlogPost` data.

```json
{
  "id": 1,
  "title": "My First Blog",
  "content": "This is the content...",
  "published_date": "2025-04-18T12:34:56Z"
}
```

---

## 📤 API Endpoints

### 1. `GET /blogposts/`

- **Description**: Retrieve a list of all blog posts.
- **Response**: 200 OK + list of serialized blog posts.

---

### 2. `POST /blogposts/`

- **Description**: Create a new blog post.
- **Body Example**:
```json
{
  "title": "New Post",
  "content": "Some interesting content."
}
```
- **Response**: 201 Created + created blog post.

---

### 3. `DELETE /blogposts/`

- **Description**: Delete **all** blog posts.
- **Response**: 204 No Content

> ⚠️ This deletes **all** blog posts. Use with caution.

---

### 4. `GET /blogposts/<id>/`

- **Description**: Retrieve a single blog post by ID.
- **Response**: 200 OK + blog post data
- **404**: If blog post is not found.

---

### 5. `PUT /blogposts/<id>/`

- **Description**: Update an entire blog post.
- **Response**: 200 OK + updated post

---

### 6. `PATCH /blogposts/<id>/`

- **Description**: Partially update a blog post.
- **Response**: 200 OK + updated post

---

### 7. `DELETE /blogposts/<id>/`

- **Description**: Delete a blog post by ID.
- **Response**: 204 No Content

---

### 8. `GET /filter-blogposts/?title=<search_term>`

- **Description**: Filter blog posts by partial match in title.
- **Query Param**: `title` (optional)
- **Example**: `/filter-blogposts/?title=django`
- **Response**: 200 OK + filtered blog posts

---




## ▶️ Running the Project

```bash
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

---

## 🧪 Testing

You can test the API with:

- **Postman**
- **cURL**
- **DRF's browsable API**

---

Let me know if you want this turned into a **Swagger/OpenAPI spec**, a **Markdown file**, or **automated tests** using Django's test client!
