---
title: Проектирование проверок на уровне модели предметной области
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Проектирование проверок на уровне модели предметной области
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: c071d269977ccecea9a7d4d79da78d7967bb1618
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105739"
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="1a3d4-103">Проектирование проверок на уровне модели предметной области</span><span class="sxs-lookup"><span data-stu-id="1a3d4-103">Designing validations in the domain model layer</span></span>

<span data-ttu-id="1a3d4-104">В DDD правила проверки можно рассматривать как инварианты.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-104">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="1a3d4-105">Главной задачей агрегата является применение инвариантов в изменениях состояния для всех сущностей внутри него.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-105">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="1a3d4-106">Сущности предметной области всегда должны быть допустимыми.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-106">Domain entities should always be valid entities.</span></span> <span data-ttu-id="1a3d4-107">Существует определенное количество инвариантов для объекта, которые всегда должны быть истинными.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-107">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="1a3d4-108">Например, для объекта позиции заказа всегда должно быть указано количество в виде положительного целого числа, а также название и цена изделия.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-108">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="1a3d4-109">Таким образом, за применение инвариантов отвечают сущности предметной области (особенно для корня агрегата), а право на существование имеет только допустимый объект сущности.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-109">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="1a3d4-110">Инвариантные правила выражаются в виде контрактов. При их нарушении вызываются исключения или выводятся уведомления.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-110">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="1a3d4-111">Это обуславливается тем, что возникает множество ошибок, поскольку объекты находятся в состоянии, в котором они никогда не должны быть.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-111">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="1a3d4-112">Далее приводится объяснение Грега Янга (Greg Young) в рамках [онлайн-обсуждения](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/).</span><span class="sxs-lookup"><span data-stu-id="1a3d4-112">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="1a3d4-113">Предположим, что у нас есть служба SendUserCreationEmailService, принимающая UserProfile... Как в этой службе можно рационализировать тот момент, что имя имеет ненулевое значение?</span><span class="sxs-lookup"><span data-stu-id="1a3d4-113">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="1a3d4-114">Нужно выполнять еще одну проверку?</span><span class="sxs-lookup"><span data-stu-id="1a3d4-114">Do we check it again?</span></span> <span data-ttu-id="1a3d4-115">Или, что более вероятно, вы просто игнорируете проверку и надеетесь на лучшее — вы надеетесь, что до отправки вам проверку выполнил кто-то другой.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-115">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="1a3d4-116">Конечно, в рамках разработки на уровне тестирования один из первых создаваемых тестов должен проверять следующее условие: если сообщение отправляется клиенту с пустым именем, должна возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-116">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="1a3d4-117">Но как только мы начинаем писать эти виды тестов снова и снова, мы понимаем, что если бы мы не разрешили использовать имя с пустым значением, всех этих тестов не было бы.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-117">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="1a3d4-118">Реализация проверок на уровне модели предметной области</span><span class="sxs-lookup"><span data-stu-id="1a3d4-118">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="1a3d4-119">Как правило, проверки обычно реализуются в конструкторах сущностей предметной области или в методах, которые могут обновлять сущность.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-119">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="1a3d4-120">Существует несколько способов реализации проверки, например проверка данных и вызов исключений, если проверка завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-120">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="1a3d4-121">Есть более сложные схемы, например использование шаблона спецификации для проверок и шаблона уведомления для возвращения коллекции ошибок вместо возвращения исключений, возникающих при каждой проверке.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-121">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="1a3d4-122">Проверка условий и создание исключений</span><span class="sxs-lookup"><span data-stu-id="1a3d4-122">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="1a3d4-123">В следующем примере кода показан простейший способ проверки сущности предметной области путем создания исключения.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-123">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="1a3d4-124">В конце этого раздела приводятся ссылки на более сложные реализации на основе шаблонов, которые обсуждались ранее.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-124">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="1a3d4-125">В более наглядном примере демонстрируется необходимость обеспечить либо неизменность внутреннего состояния, либо возникновение всех изменений для метода.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-125">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="1a3d4-126">Например, в следующей реализации объект останется в недопустимом состоянии:</span><span class="sxs-lookup"><span data-stu-id="1a3d4-126">For example, the following implementation would leave the object in an invalid state:</span></span>

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

<span data-ttu-id="1a3d4-127">Если состояние имеет недопустимое значение, значит, первая строка адреса и город уже были изменены.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-127">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="1a3d4-128">В этом случае адрес может стать недействительным.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-128">That might make the address invalid.</span></span>

<span data-ttu-id="1a3d4-129">Аналогичный подход можно использовать в конструкторе сущности, когда вызывается исключение для проверки допустимости сущности после ее создания.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-129">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="1a3d4-130">Использование атрибутов проверки атрибутов в модели на основе заметок к данным</span><span class="sxs-lookup"><span data-stu-id="1a3d4-130">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="1a3d4-131">Следующий подход заключается в использовании атрибутов проверки на основании заметок к данным.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-131">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="1a3d4-132">Атрибуты проверки — это способ настройки проверки модели таким образом, чтобы она по существу была похожа на проверку полей в таблицах базы данных.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-132">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="1a3d4-133">Сюда входят ограничения, например назначение типов данных или обязательных полей.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-133">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="1a3d4-134">Другие виды проверок включают в себя применение шаблонов к данным, таких как номера кредитных карт, номера телефонов или адреса электронной почты, для реализации бизнес-правил.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-134">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="1a3d4-135">Атрибуты проверки упрощают применение требований.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-135">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="1a3d4-136">Однако, как показано в следующем коде, этот подход может быть слишком интрузивным для модели DDD, так как он принимает зависимость от ModelState.IsValid из Microsoft.AspNetCore.Mvc.ModelState, который следует вызывать из контроллеров MVC.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-136">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="1a3d4-137">Проверка модели проводится перед вызовом каждого действия контроллера. Метод действия отвечает за проверку результата вызова метода ModelState.IsValid и соответствующую реакцию.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-137">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="1a3d4-138">Решение о его использовании зависит от того, насколько тесно модель должна быть связана с этой инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-138">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

<span data-ttu-id="1a3d4-139">Однако с точки зрения DDD наилучшая оптимизация модели предметной области достигается за счет использования исключений в методах поведения сущности или при реализации шаблонов спецификации и уведомления для применения правил проверки.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-139">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="1a3d4-140">Системы проверок, такие как заметки к данным в ASP.NET Core, или другие системы, такие как FluentValidation, предъявляют требование к вызову платформы приложений.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-140">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="1a3d4-141">Например, при вызове метода ModelState.IsValid в заметках к данным необходимо вызвать контроллеры ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-141">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="1a3d4-142">Заметки к данным целесообразно использовать на уровне приложения в классах ViewModel (а не в сущностях предметной области), которые будут принимать входные данные, чтобы осуществлять проверку модели на уровне пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-142">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="1a3d4-143">Однако это не должно происходить при исключении проверки в модели предметной области.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-143">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="1a3d4-144">Проверка сущностей путем реализации шаблона спецификации и шаблона уведомлений</span><span class="sxs-lookup"><span data-stu-id="1a3d4-144">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="1a3d4-145">Наконец, более сложный подход к реализации проверок в модели предметной области заключается в реализации шаблона спецификации вместе с шаблоном уведомления, как описано в некоторых приведенных далее дополнительных ресурсах.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-145">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="1a3d4-146">Следует отметить, что можно использовать только один из этих шаблонов. Например, можно выполнять проверки вручную с помощью операторов управления и применять шаблон уведомления для сбора и возвращения списка ошибок, обнаруженных при проверке.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-146">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="1a3d4-147">Использование отложенной проверки в предметной области</span><span class="sxs-lookup"><span data-stu-id="1a3d4-147">Using deferred validation in the domain</span></span>

<span data-ttu-id="1a3d4-148">Существуют различные методы обработки отложенных проверок в предметной области.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-148">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="1a3d4-149">Вон Вернон (Vaughn Vernon) рассматривает их в своей книге [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577) (Реализация разработки на основе предметной области) в разделе, посвященном проверке.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-149">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="1a3d4-150">Двухэтапная проверка</span><span class="sxs-lookup"><span data-stu-id="1a3d4-150">Two-step validation</span></span>

<span data-ttu-id="1a3d4-151">Рассмотрим двухэтапную проверку.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-151">Also consider two-step validation.</span></span> <span data-ttu-id="1a3d4-152">Используйте проверку на уровне поля для объектов передачи данных (DTO) команд и проверку на уровне предметной области внутри сущностей.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-152">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="1a3d4-153">Это можно сделать путем возвращения результирующего объекта, а не исключений, чтобы упростить процесс обработки ошибок, обнаруженных при проверке.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-153">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="1a3d4-154">Например, с помощью проверки полей с заметками к данным вы не дублируете определение проверки.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-154">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="1a3d4-155">Однако при использовании DTO (к примеру, команд и ViewModel) выполнение может осуществляться как на стороне сервера, так и на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="1a3d4-155">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a3d4-156">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="1a3d4-156">Additional resources</span></span>

-   <span data-ttu-id="1a3d4-157">**Рэйчел Аппель (Rachel Appel). Общие сведения о проверке модели в ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="1a3d4-157">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="1a3d4-158">**Рик Андерсон (Rick Anderson). Добавление проверки**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="1a3d4-158">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="1a3d4-159">**Мартин Фоулер (Martin Fowler). Замена исключений уведомлениями в проверках**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="1a3d4-159">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="1a3d4-160">**Спецификация и шаблоны уведомлений**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="1a3d4-160">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="1a3d4-161">**Лев Городинский (Lev Gorodinski). Проверка в проблемно-ориентированном программировании (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="1a3d4-161">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="1a3d4-162">**Колин Джек (Colin Jack) Проверка модели предметной области**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="1a3d4-162">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="1a3d4-163">**Джимми Богард (Jimmy Bogard). Проверка в мире DDD**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="1a3d4-163">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="1a3d4-164">[Назад](enumeration-classes-over-enum-types.md)
[Вперед](client-side-validation.md)</span><span class="sxs-lookup"><span data-stu-id="1a3d4-164">[Previous](enumeration-classes-over-enum-types.md)
[Next](client-side-validation.md)</span></span>
