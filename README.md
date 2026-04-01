### Use Case Диаграмма
```mermaid
graph LR
    Seller((Продавец)) --- UC1(Создать товар)
    Seller --- UC2(Просмотреть статус)
    UC1 -.->|include| UC3(Загрузить фото)
    UC1 -.->|include| UC4(Выбрать категорию)
    UC1 --> Mod[Сервис модерации]
    Mod --> Shop(Витрина маркетплейса)
