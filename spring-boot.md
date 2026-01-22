# Spring Boot

## Cascade

- Types: `PERSIST` saves children; `MERGE` updates; `REMOVE` deletes; `REFRESH` reloads; `DETACH` drops from context; `ALL` includes all.
- `orphanRemoval = true` auto-deletes children removed from a parent collection.

```java
@OneToMany(mappedBy = "order", cascade = CascadeType.ALL, orphanRemoval = true)
private List<OrderItem> items = new ArrayList<>();
```

- Parent owns the child lifecycle = children are created/updated/deleted through the parent and should not outlive it; skip cascade for shared/many-to-many.
- Keep cascading inside a single service-layer transaction.

## Fetch

- Fetch types: `LAZY` loads when accessed; `EAGER` loads immediately. Default is EAGER for `@ManyToOne/@OneToOne`, LAZY for `@OneToMany/@ManyToMany`.
- Prefer explicit `fetch = FetchType.LAZY` on associations and load what you need with fetch joins or `@EntityGraph`.

```java
@ManyToOne(fetch = FetchType.LAZY)
private Customer customer;

@Query("select o from Order o join fetch o.customer where o.id = :id")
Optional<Order> findWithCustomer(@Param("id") Long id);
```

- Avoid `EAGER` on collections; it can explode queries and cause N+1 issues.
