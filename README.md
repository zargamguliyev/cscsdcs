### Use Case Диаграмма
```mermaid
graph LR
    Seller((Продавец)) --- UC1(Создать товар)
    Seller --- UC2(Просмотреть статус)
    UC1 -.->|include| UC3(Загрузить фото)
    UC1 -.->|include| UC4(Выбрать категорию)
    UC1 --> Mod[Сервис модерации]
    Mod --> Shop(Витрина маркетплейса)

---

### dncjdnjc

useCaseDiagram
    actor "Продавец" as Seller
    actor "Сервис модерации" as ModService
    actor "Витрина (Покупатель)" as Storefront

    package "Личный кабинет продавца" {
        usecase "Создать карточку товара" as UC1
        usecase "Загрузить медиафайлы" as UC2
        usecase "Выбрать категорию" as UC3
        usecase "Отправить на модерацию" as UC4
        usecase "Сохранить черновик" as UC5
        usecase "Просмотреть статус" as UC6
    }

    Seller --> UC1
    UC1 ..> UC2 : <<include>>
    UC1 ..> UC3 : <<include>>
    Seller --> UC4
    Seller --> UC5
    Seller --> UC6

    UC4 --> ModService : "Передача данных"
    ModService --> Storefront : "Публикация при успехе"

