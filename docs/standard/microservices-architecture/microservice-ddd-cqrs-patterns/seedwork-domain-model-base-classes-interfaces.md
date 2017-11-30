---
title: "Seedwork (многократно используемые базовые классы и интерфейсы для модели домена)"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Seedwork (многократно используемые базовые классы и интерфейсы для модели домена)"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 17602d94ea167997389a77f0d2358326258a8219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork (многократно используемые базовые классы и интерфейсы для модели домена)

Папка решения содержит *SeedWork* папки. *SeedWork* папка содержит пользовательские базовые классы, которые можно использовать в качестве базы для вашего домена сущностей и объектов значение. Используйте эти базовые классы, поэтому нет избыточный код в класс объекта для каждого домена. Папка для этих типов классов называется *SeedWork* , а не то, как *Framework*. Он вызывается *SeedWork* , так как папка содержит только небольшое подмножество многократно используемые классы, которые действительно не может считаться платформу. *Seedwork* термин введенный [Майкла Физерса](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) и Кроме того, [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) , но можно также назвать эту папку Общие, SharedKernel, или же.

Рис. 9-12 показывает классы, формирующие seedwork модели домена в микрослужбу порядка сортировки. Он имеет несколько пользовательских базовых классов сущностей, ValueObject и перечисления, а также несколько интерфейсов. Эти интерфейсы (IRepository и IUnitOfWork) уровень инфраструктуры сообщают о том, что должен быть реализован. Эти интерфейсы также используются через внедрения зависимости от уровня приложения.

![](./media/image13.PNG)

**Рис. 9-12**. Образец набора домена модели «seedwork» базовые классы и интерфейсы

Это тип, копировать и вставить многократного использования, многие разработчики совместно использовать проектов, не формальных framework. Может иметь seedworks в любой уровень или в библиотеке. Тем не менее если набор классов и интерфейсов получает достаточно большой, может потребоваться создание одной библиотеке классов.

## <a name="the-custom-entity-base-class"></a>Пользовательские сущности базового класса

Ниже приведен пример базового класса сущности расположения кода, который может использоваться так же, как любой сущности домена, такие как идентификатор сущности, [операторы равенства](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)и т. д.

```csharp
// ENTITY FRAMEWORK CORE 1.1
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;

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
                _requestedHashCode = this.Id.GetHashCode() \^ 31;
            // XOR for random distribution. See:
            // http://blogs.msdn.com/b/ericlippert/archive/2011/02/28/guidelines-and-rules-for-gethashcode.aspx
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }

    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null)) ? true : false;
        else
            return left.Equals(right);
    }

    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Репозиторий контрактов (интерфейсы), в уровне модели домена

Репозиторий контракты являются просто интерфейсы платформы .NET, представляющие контрактом требований репозиториями для каждого статистического выражения. Сами репозиториями с EF основного кода или другие зависимости инфраструктуры и кодом, не должен быть реализован в пределах модели домена; репозиториями только должен реализовывать интерфейсы, определенных пользователем.

Разделенные интерфейс является шаблон, связанные с такой подход (разместите интерфейсы репозитория в уровне модели домена). Как [описано](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) по Martin Fowler «интерфейс Separated используется для определения интерфейса в одном пакета, но реализовать его в другой. Таким образом клиент, который требуется зависимостей на интерфейс может быть малейшего реализации.»

Следующий шаблон запятыми интерфейс позволяет на уровне приложения (в данном случае проект веб-API для микрослужбу) на зависимость для требований, которые определены в модели домена, а не прямой зависимости инфраструктуры и сохраняемости слой. Кроме того, можно использовать для изоляции реализацию, которая реализована в инфраструктуре внедрения зависимостей и уровень сохраняемости с помощью репозиториев.

Например в следующем примере с помощью интерфейса IOrderRepository определяется какие операции OrderRepository класс должен реализовывать на уровне инфраструктуры. В текущей реализации приложения код просто необходимо добавить порядок в базе данных, так как запросы являются следующие разбиение CQS подход и обновления заказов не реализована.

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
}

public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Мартин Фоулер (Martin Fowler). Интерфейс, разделенных запятыми. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)


>[!div class="step-by-step"]
[Предыдущие] (net-core микрослужбу домена model.md) [Далее] (objects.md реализуйте значение)
