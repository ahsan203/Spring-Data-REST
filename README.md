🔹 Spring Data REST vs Spring Data JPA :
-------------------------------------------

 **Spring Data REST**, you don’t need to write controllers or service classes for CRUD at all :
-----------------------------------------------------------------------------------------------
1. **Entity class** → defines the structure of your data (e.g., `Product`, `Task`).
2. **Repository interface** → extends `JpaRepository`, `CrudRepository`, or `MongoRepository`.
That’s it!
Spring Data REST automatically:

3. Exposes REST endpoints (like `/products`, `/products/{id}`).
4.Provides built-in **CRUD operations** (`GET`, `POST`, `PUT`, `PATCH`, `DELETE`).
5.Handles **paging, sorting, and filtering**.

Example:
----------
@Entity
public class Product {
    @Id
    @GeneratedValue
    private Long id;
    private String name;
    private Double price;
}
public interface ProductRepository extends JpaRepository<Product, Long> {
}

Spring Data REST:
-------------------
1) Auto-generates REST APIs directly from repositories.
2) Good for quick CRUD prototypes, demos, or admin tools.
3) Rare in production (less control, security & customization is hard).

Spring Data JPA:
----------------
1) Standard for real-world projects.
2) You write repositories + services + controllers.
3) Gives full control over queries, business logic, validation, security.
4) Widely used in industry (90% cases).

✅ In Short:
--------------
In Spring, Spring Data JPA is the real-world standard, while Spring Data REST is mostly for quick prototypes.
