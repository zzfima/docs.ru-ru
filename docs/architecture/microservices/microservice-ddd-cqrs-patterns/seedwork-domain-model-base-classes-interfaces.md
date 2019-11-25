---
title: Seedwork (многократно используемые базовые классы и интерфейсы для модели предметной области)
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Использование концепции seedwork в качестве отправной точки для запуска реализации для модели предметной области, ориентированной на DDD.
ms.date: 10/08/2018
ms.openlocfilehash: f53988b92a05fb54f3f05d9f463450d1a11a0843
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737214"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork (многократно используемые базовые классы и интерфейсы для модели предметной области)

В папке решения имеется папка *SeedWork*. В этой папке содержатся пользовательские базовые классы, которые можно использовать в качестве основы для сущностей предметной области и объектов значений. Используйте эти базовые классы, чтобы не было избыточного кода в классе объектов каждого домена. Папка для этих типов классов называется *SeedWork*, а не как-нибудь похоже на *Framework*. Эта папка называется *SeedWork*, так как в ней содержится только небольшое подмножество многократно используемых классов, которое в действительности не может считаться структурой. Термин *Seedwork* был введен [Майклом Фезерсом (Michael Feathers)](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) и получил распространение благодаря [Мартину Фаулеру (Martin Fowler)](https://martinfowler.com/bliki/Seedwork.html), но можно также назвать эту папку Common, SharedKernel или аналогичным образом.

На рис. 7-12 показаны классы, формирующие набор seedwork модели предметной области в микрослужбе заказов. В нем имеется несколько пользовательских базовых классов, таких как Entity, ValueObject и Enumeration, а также несколько интерфейсов. Эти интерфейсы (IRepository и IUnitOfWork) информируют уровень инфраструктуры о том, что должно быть реализовано. Эти интерфейсы также используются через внедрение зависимостей из прикладного уровня.

:::image type="complex" source="./media/seedwork-domain-model-base-classes-interfaces/vs-solution-seedwork-classes.png" alt-text="Снимок экрана: классы, содержащиеся в папке SeedWork.":::
Подробное содержимое папки SeedWork, содержащей базовые классы и интерфейсы: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs и ValueObject.cs.
:::image-end:::

**Рис. 7-12**. Пример набора базовых классов и интерфейсов "seedwork" модели предметной области

Это разновидность копирования и вставки, которую многие разработчики используют в проектах, а не формальная структура. Вы можете иметь наборы seedwork на любом уровне или в любой библиотеке. Однако если набор классов и интерфейсов становится достаточно большим, вам может понадобиться создать единую библиотеку классов.

## <a name="the-custom-entity-base-class"></a>Пользовательский базовый класс Entity

Следующий код представляет пример базового класса Entity, где можно разместить код, который может многократно использоваться тем же способом в любой сущности предметной области, например идентификатор сущности, [операторы равенства](../../../csharp/language-reference/operators/equality-operators.md), список событий предметной области по сущностям и т. п.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE (1.1 and later)
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;
    private List<INotification> _domainEvents;
    public virtual int Id
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public List<INotification> DomainEvents => _domainEvents;
    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }
    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }

    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() ^ 31;
            // XOR for random distribution. See:
            // https://blogs.msdn.microsoft.com/ericlippert/2011/02/28/guidelines-and-rules-for-gethashcode/
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null));
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

Предыдущий код, использующий список событий предметной области по сущностям, будет рассматриваться в следующих разделах при изучении событий предметной области.

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Контракты репозиториев (интерфейсы) на уровне модели предметной области

Контракты репозиториев являются просто интерфейсами .NET, выражающими требования контрактов репозиториев, которые должны использоваться для каждого агрегата.

Сами по себе репозитории, с кодом EF Core или любыми другими зависимостями инфраструктуры и кодом (Linq, SQL и т. п.), не должны реализовываться в рамках модели предметной области; репозитории должны только реализовывать интерфейсы, определенные вами в модели предметной области.

С этим подходом (размещение интерфейсов репозиториев на уровне модели предметной области) связан шаблон Separated Interface (разделенного интерфейса). Как [объяснил](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) Мартин Фаулер, "используйте шаблон Separated Interface для определения интерфейса в одном пакете и реализации его в другом. Таким образом, клиент, которому требуется зависимость от интерфейса, может ничего не знать о реализации".

Использование шаблона Separated Interface позволяет прикладному уровню (в данном случае это проект веб-API для микрослужбы) иметь зависимость от требований, определенных в модели предметной области, но не прямую зависимость от уровня инфраструктуры или существования. Кроме того, вы можете использовать внедрение зависимостей для изоляции реализации, которая реализована на уровне инфраструктуры или существования с помощью репозиториев.

Например, в следующем примере с интерфейсом IOrderRepository определяется, какие операции класс OrderRepository должен будет реализовывать на уровне инфраструктуры. В текущей реализации приложения код должен просто добавлять или обновлять заказы в базе данных, так как согласно упрощенному подходу CQRS запросы разделяются.

```csharp
// Defined at IOrderRepository.cs
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);

    void Update(Order order);

    Task<Order> GetAsync(int orderId);
}

// Defined at IRepository.cs (Part of the Domain Seedwork)
public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a>Дополнительные ресурсы

- **Мартин Фоулер (Martin Fowler). Отделяемый интерфейс.** \
  <https://www.martinfowler.com/eaaCatalog/separatedInterface.html>

>[!div class="step-by-step"]
>[Назад](net-core-microservice-domain-model.md)
>[Вперед](implement-value-objects.md)
