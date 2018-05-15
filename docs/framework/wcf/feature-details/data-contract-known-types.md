---
title: Известные типы контрактов данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], known types
- KnownTypeAttribute [WCF]
- KnownTypes [WCF]
ms.assetid: 1a0baea1-27b7-470d-9136-5bbad86c4337
ms.openlocfilehash: 00ae32ff394b1ce2acb38fb237527e934934b935
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-contract-known-types"></a><span data-ttu-id="fa324-102">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="fa324-102">Data Contract Known Types</span></span>
<span data-ttu-id="fa324-103">Класс <xref:System.Runtime.Serialization.KnownTypeAttribute> позволяет заранее задавать типы, которые следует рассматривать при десериализации.</span><span class="sxs-lookup"><span data-stu-id="fa324-103">The <xref:System.Runtime.Serialization.KnownTypeAttribute> class allows you to specify, in advance, the types that should be included for consideration during deserialization.</span></span> <span data-ttu-id="fa324-104">Рабочий пример см. в разделе [Known Types](../../../../docs/framework/wcf/samples/known-types.md) .</span><span class="sxs-lookup"><span data-stu-id="fa324-104">For a working example, see the [Known Types](../../../../docs/framework/wcf/samples/known-types.md) example.</span></span>  
  
 <span data-ttu-id="fa324-105">Обычно при передаче параметров и возвращаемых значений между клиентом и службой обе конечные точки совместно используют все контракты данных, относящиеся к передаваемым данным.</span><span class="sxs-lookup"><span data-stu-id="fa324-105">Normally, when passing parameters and return values between a client and a service, both endpoints share all of the data contracts of the data to be transmitted.</span></span> <span data-ttu-id="fa324-106">Однако в следующих ситуациях это не так:</span><span class="sxs-lookup"><span data-stu-id="fa324-106">However, this is not the case in the following circumstances:</span></span>  
  
-   <span data-ttu-id="fa324-107">Контракт отправляемых данных унаследован из контракта ожидаемых данных.</span><span class="sxs-lookup"><span data-stu-id="fa324-107">The sent data contract is derived from the expected data contract.</span></span> <span data-ttu-id="fa324-108">Дополнительные сведения см. в разделе о наследования в [эквивалентность контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)).</span><span class="sxs-lookup"><span data-stu-id="fa324-108">For more information, see the section about inheritance in [Data Contract Equivalence](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)).</span></span> <span data-ttu-id="fa324-109">В этом случае контракт передаваемых данных отличается от контракта данных, ожидаемого принимающей конечной точкой;</span><span class="sxs-lookup"><span data-stu-id="fa324-109">In that case, the transmitted data does not have the same data contract as expected by the receiving endpoint.</span></span>  
  
-   <span data-ttu-id="fa324-110">объявленный тип передаваемых данных является интерфейсом, а не классом, структурой или перечислением.</span><span class="sxs-lookup"><span data-stu-id="fa324-110">The declared type for the information to be transmitted is an interface, as opposed to a class, structure, or enumeration.</span></span> <span data-ttu-id="fa324-111">Поэтому невозможно заранее знать, какой именно из реализуемых этим интерфейсом типов будет передан, а следовательно принимающая конечная точка не может заранее определить контракт передаваемых данных;</span><span class="sxs-lookup"><span data-stu-id="fa324-111">Therefore, it cannot be known in advance which type that implements the interface is actually sent and therefore, the receiving endpoint cannot determine in advance the data contract for the transmitted data.</span></span>  
  
-   <span data-ttu-id="fa324-112">объявлен тип передаваемых данных <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="fa324-112">The declared type for the information to be transmitted is <xref:System.Object>.</span></span> <span data-ttu-id="fa324-113">Поскольку каждый тип наследуется от класса <xref:System.Object>, невозможно заранее знать, какой именно тип будет передан, а следовательно принимающая конечная точка не может заранее определить контракт передаваемых данных.</span><span class="sxs-lookup"><span data-stu-id="fa324-113">Because every type inherits from <xref:System.Object>, and it cannot be known in advance which type is actually sent, the receiving endpoint cannot determine in advance the data contract for the transmitted data.</span></span> <span data-ttu-id="fa324-114">Это частный случай первого варианта: каждый контракт данных наследует от контракта данных по умолчанию (пустого контракта), который создается для класса <xref:System.Object>;</span><span class="sxs-lookup"><span data-stu-id="fa324-114">This is a special case of the first item: Every data contract derives from the default, a blank data contract that is generated for <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="fa324-115">у некоторых типов, включающих типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , имеются члены, относящиеся к одной из указанных выше трех категорий.</span><span class="sxs-lookup"><span data-stu-id="fa324-115">Some types, which include [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types, have members that are in one of the preceding three categories.</span></span> <span data-ttu-id="fa324-116">Например, класс <xref:System.Collections.Hashtable> использует класс <xref:System.Object> для хранения фактических объектов в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="fa324-116">For example, <xref:System.Collections.Hashtable> uses <xref:System.Object> to store the actual objects in the hash table.</span></span> <span data-ttu-id="fa324-117">При сериализации таких типов принимающая сторона не может заранее определить контракт данных таких членов.</span><span class="sxs-lookup"><span data-stu-id="fa324-117">When serializing these types, the receiving side cannot determine in advance the data contract for these members.</span></span>  
  
## <a name="the-knowntypeattribute-class"></a><span data-ttu-id="fa324-118">Класс KnownTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="fa324-118">The KnownTypeAttribute Class</span></span>  
 <span data-ttu-id="fa324-119">Когда данные прибывают в принимающую конечную точку, среда выполнения WCF предпринимает попытку десериализовать данные в экземпляр типа среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="fa324-119">When data arrives at a receiving endpoint, the WCF runtime attempts to deserialize the data into an instance of a common language runtime (CLR) type.</span></span> <span data-ttu-id="fa324-120">Тип, экземпляр которого создается в результате десериализации, выбирается в первую очередь по результатам проверки входящего сообщения с целью определения контракта данных, которому соответствует содержимое сообщения.</span><span class="sxs-lookup"><span data-stu-id="fa324-120">The type that is instantiated for deserialization is chosen by first inspecting the incoming message to determine the data contract to which the contents of the message conform.</span></span> <span data-ttu-id="fa324-121">После этого система десериализации пытается найти тип среды CLR, который реализует контракт данных, совместимый с содержимым сообщения.</span><span class="sxs-lookup"><span data-stu-id="fa324-121">The deserialization engine then attempts to find a CLR type that implements a data contract compatible with the message contents.</span></span> <span data-ttu-id="fa324-122">Набор потенциальных типов, которые система десериализации считает допустимыми в результате выполнения этих операций, называется набором "известных типов" десериализатора.</span><span class="sxs-lookup"><span data-stu-id="fa324-122">The set of candidate types that the deserialization engine allows for during this process is referred to as the deserializer's set of "known types."</span></span>  
  
 <span data-ttu-id="fa324-123">Один из способов уведомления десериализатора о типе - использовать класс <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fa324-123">One way to let the deserialization engine know about a type is by using the <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span></span> <span data-ttu-id="fa324-124">Этот атрибут нельзя применять к отдельным членам, но следует применять только к целым типам контрактов данных.</span><span class="sxs-lookup"><span data-stu-id="fa324-124">The attribute cannot be applied to individual data members, only to whole data contract types.</span></span> <span data-ttu-id="fa324-125">Атрибут применяется к *внешнему типу* , который может быть классом или структурой.</span><span class="sxs-lookup"><span data-stu-id="fa324-125">The attribute is applied to an *outer type* that can be a class or a structure.</span></span> <span data-ttu-id="fa324-126">На самом базовом уровне применение этого атрибута помечает тип в качестве "известного типа".</span><span class="sxs-lookup"><span data-stu-id="fa324-126">In its most basic usage, applying the attribute specifies a type as a "known type."</span></span> <span data-ttu-id="fa324-127">В результате известный тип становится частью набора известных типов всякий раз, когда происходит десериализация объекта внешнего типа или любого объекта, являющегося членом известного типа.</span><span class="sxs-lookup"><span data-stu-id="fa324-127">This causes the known type to be a part of the set of known types whenever an object of the outer type or any object referred to through its members is being deserialized.</span></span> <span data-ttu-id="fa324-128">К одному и тому же типу можно применить несколько атрибутов <xref:System.Runtime.Serialization.KnownTypeAttribute> .</span><span class="sxs-lookup"><span data-stu-id="fa324-128">More than one <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute can be applied to the same type.</span></span>  
  
## <a name="known-types-and-primitives"></a><span data-ttu-id="fa324-129">Известные типы и примитивы</span><span class="sxs-lookup"><span data-stu-id="fa324-129">Known Types and Primitives</span></span>  
 <span data-ttu-id="fa324-130">Типы-примитивы, а также некоторые типы, с которыми обращаются как с примитивами (например, <xref:System.DateTime> и <xref:System.Xml.XmlElement>), всегда являются "известными", и их никогда не нужно добавлять с помощью описанного механизма.</span><span class="sxs-lookup"><span data-stu-id="fa324-130">Primitive types, as well as certain types treated as primitives (for example, <xref:System.DateTime> and <xref:System.Xml.XmlElement>) are always "known" and never have to be added through this mechanism.</span></span> <span data-ttu-id="fa324-131">Однако массивы типов-примитивов нужно добавлять в явном виде.</span><span class="sxs-lookup"><span data-stu-id="fa324-131">However, arrays of primitive types have to be added explicitly.</span></span> <span data-ttu-id="fa324-132">Большинство коллекций считаются эквивалентами массивов.</span><span class="sxs-lookup"><span data-stu-id="fa324-132">Most collections are considered equivalent to arrays.</span></span> <span data-ttu-id="fa324-133">(Неуниверсальные коллекции считаются эквивалентами массивов <xref:System.Object>.)</span><span class="sxs-lookup"><span data-stu-id="fa324-133">(Non-generic collections are considered equivalent to arrays of <xref:System.Object>).</span></span> <span data-ttu-id="fa324-134">Пример использования примитивов, массивов примитивов и коллекций примитивов см. в примере 4.</span><span class="sxs-lookup"><span data-stu-id="fa324-134">For an example of the using primitives, primitive arrays, and primitive collections, see Example 4.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa324-135">В отличие от других типов-примитивов структура <xref:System.DateTimeOffset> по умолчанию не является известным типом, поэтому ее необходимо вручную добавлять в список известных типов.</span><span class="sxs-lookup"><span data-stu-id="fa324-135">Unlike other primitive types, the <xref:System.DateTimeOffset> structure is not a known type by default, so it must be manually added to the list of known types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fa324-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="fa324-136">Examples</span></span>  
 <span data-ttu-id="fa324-137">Ниже приведены примеры использования класса <xref:System.Runtime.Serialization.KnownTypeAttribute> .</span><span class="sxs-lookup"><span data-stu-id="fa324-137">The following examples show the <xref:System.Runtime.Serialization.KnownTypeAttribute> class in use.</span></span>  
  
#### <a name="example-1"></a><span data-ttu-id="fa324-138">Пример 1</span><span class="sxs-lookup"><span data-stu-id="fa324-138">Example 1</span></span>  
 <span data-ttu-id="fa324-139">Имеется три класса, связанных отношениями наследования.</span><span class="sxs-lookup"><span data-stu-id="fa324-139">There are three classes with an inheritance relationship.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#1)]
 [!code-vb[C_KnownTypeAttribute#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#1)]  
  
 <span data-ttu-id="fa324-140">Показанный ниже класс `CompanyLogo` можно сериализовать; однако он не может быть сериализован, если член `ShapeOfLogo` имеет значение `CircleType` или `TriangleType` , поскольку система десериализации не распознает типы с именами контрактов данных "Circle" и "Triangle".</span><span class="sxs-lookup"><span data-stu-id="fa324-140">The following `CompanyLogo` class can be serialized, but cannot be deserialized if the `ShapeOfLogo` member is set to either a `CircleType` or a `TriangleType` object, because the deserialization engine does not recognize any types with data contract names "Circle" or "Triangle."</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#2)]
 [!code-vb[C_KnownTypeAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#2)]  
  
 <span data-ttu-id="fa324-141">В следующем примере кода показано, как правильно описать тип `CompanyLogo` .</span><span class="sxs-lookup"><span data-stu-id="fa324-141">The correct way to write the `CompanyLogo` type is shown in the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#3)]
 [!code-vb[C_KnownTypeAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#3)]  
  
 <span data-ttu-id="fa324-142">Когда происходит десериализация внешнего типа `CompanyLogo2` , система десериализации знает о типах `CircleType` и `TriangleType` и поэтому может найти контракты данных, соответствующие типам "Circle" и "Triangle".</span><span class="sxs-lookup"><span data-stu-id="fa324-142">Whenever the outer type `CompanyLogo2` is being deserialized, the deserialization engine knows about `CircleType` and `TriangleType` and, therefore, is able to find matching types for the "Circle" and "Triangle" data contracts.</span></span>  
  
#### <a name="example-2"></a><span data-ttu-id="fa324-143">Пример 2</span><span class="sxs-lookup"><span data-stu-id="fa324-143">Example 2</span></span>  
 <span data-ttu-id="fa324-144">В следующем примере, даже если оба типа `CustomerTypeA` и `CustomerTypeB` имеют контракт данных `Customer` , при десериализации типа `CustomerTypeB` будет создаваться экземпляр `PurchaseOrder` , поскольку системе десериализации известен только тип `CustomerTypeB` .</span><span class="sxs-lookup"><span data-stu-id="fa324-144">In the following example, even though both `CustomerTypeA` and `CustomerTypeB` have the `Customer` data contract, an instance of `CustomerTypeB` is created whenever a `PurchaseOrder` is deserialized, because only `CustomerTypeB` is known to the deserialization engine.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#4)]
 [!code-vb[C_KnownTypeAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#4)]  
  
#### <a name="example-3"></a><span data-ttu-id="fa324-145">Пример 3</span><span class="sxs-lookup"><span data-stu-id="fa324-145">Example 3</span></span>  
 <span data-ttu-id="fa324-146">В следующем примере тип <xref:System.Collections.Hashtable> хранит содержимое в виде <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="fa324-146">In the following example, a <xref:System.Collections.Hashtable> stores its contents internally as <xref:System.Object>.</span></span> <span data-ttu-id="fa324-147">Для десериализации хэш-таблицы системе десериализации должен быть известен набор возможных типов, которые представляются этим типом.</span><span class="sxs-lookup"><span data-stu-id="fa324-147">To successfully deserialize a hash table, the deserialization engine must know the set of possible types that can occur there.</span></span> <span data-ttu-id="fa324-148">В данном случае нам известно, что в объекте `Book` хранятся только объекты `Magazine` и `Catalog`, поэтому они добавляются с помощью атрибута <xref:System.Runtime.Serialization.KnownTypeAttribute> .</span><span class="sxs-lookup"><span data-stu-id="fa324-148">In this case, we know in advance that only `Book` and `Magazine` objects are stored in the `Catalog`, so those are added using the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#5)]
 [!code-vb[C_KnownTypeAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#5)]  
  
#### <a name="example-4"></a><span data-ttu-id="fa324-149">Пример 4</span><span class="sxs-lookup"><span data-stu-id="fa324-149">Example 4</span></span>  
 <span data-ttu-id="fa324-150">В следующем примере контракт данных хранит число и операцию, которую следует выполнить над этим числом.</span><span class="sxs-lookup"><span data-stu-id="fa324-150">In the following example, a data contract stores a number and an operation to perform on the number.</span></span> <span data-ttu-id="fa324-151">Член данных `Numbers` может быть целым числом, массивом целых чисел или объектом <xref:System.Collections.Generic.List%601> , содержащим целые числа.</span><span class="sxs-lookup"><span data-stu-id="fa324-151">The `Numbers` data member can be an integer, an array of integers, or a <xref:System.Collections.Generic.List%601> that contains integers.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="fa324-152">Работает только на стороне клиента, если SVCUTIL.EXE используется для формирования учетной записи-посредника WCF.</span><span class="sxs-lookup"><span data-stu-id="fa324-152">This will only work on the client side if SVCUTIL.EXE is used to generate a WCF proxy.</span></span> <span data-ttu-id="fa324-153">SVCUTIL.EXE извлекает метаданные из службы, включая любые известные типы.</span><span class="sxs-lookup"><span data-stu-id="fa324-153">SVCUTIL.EXE retrieves metadata from the service including any known types.</span></span> <span data-ttu-id="fa324-154">Без этой информации клиент не сможет десериализовать типы.</span><span class="sxs-lookup"><span data-stu-id="fa324-154">Without this information a client will not be able to deserialize the types.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#6)]
 [!code-vb[C_KnownTypeAttribute#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#6)]  
  
 <span data-ttu-id="fa324-155">Ниже показан код приложения.</span><span class="sxs-lookup"><span data-stu-id="fa324-155">This is the application code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#7)]
 [!code-vb[C_KnownTypeAttribute#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#7)]  
  
## <a name="known-types-inheritance-and-interfaces"></a><span data-ttu-id="fa324-156">Известные типы, наследование и интерфейсы</span><span class="sxs-lookup"><span data-stu-id="fa324-156">Known Types, Inheritance, and Interfaces</span></span>  
 <span data-ttu-id="fa324-157">Когда известный тип связывается с конкретным типом с помощью атрибута `KnownTypeAttribute` , он также связывается со всеми производными типами этого типа.</span><span class="sxs-lookup"><span data-stu-id="fa324-157">When a known type is associated with a particular type using the `KnownTypeAttribute` attribute, the known type is also associated with all of the derived types of that type.</span></span> <span data-ttu-id="fa324-158">См., например, следующий код.</span><span class="sxs-lookup"><span data-stu-id="fa324-158">For example, see the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#8)]
 [!code-vb[C_KnownTypeAttribute#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#8)]  
  
 <span data-ttu-id="fa324-159">Класс `DoubleDrawing` не требует, чтобы атрибут `KnownTypeAttribute` использовал типы `Square` и `Circle` в поле `AdditionalShape` , поскольку эти атрибуты уже применены в базовом классе (`Drawing`).</span><span class="sxs-lookup"><span data-stu-id="fa324-159">The `DoubleDrawing` class does not require the `KnownTypeAttribute` attribute to use `Square` and `Circle` in the `AdditionalShape` field, because the base class (`Drawing`) already has these attributes applied.</span></span>  
  
 <span data-ttu-id="fa324-160">Известные типы можно связывать только с классами и структурами, но не с интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="fa324-160">Known types can be associated only with classes and structures, not interfaces.</span></span>  
  
## <a name="known-types-using-open-generic-methods"></a><span data-ttu-id="fa324-161">Известные типы и открытые универсальные методы</span><span class="sxs-lookup"><span data-stu-id="fa324-161">Known Types Using Open Generic Methods</span></span>  
 <span data-ttu-id="fa324-162">Может возникнуть необходимость добавить в качестве известного типа универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="fa324-162">It may be necessary to add a generic type as a known type.</span></span> <span data-ttu-id="fa324-163">Однако открытый универсальный тип невозможно передать в атрибут `KnownTypeAttribute` в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="fa324-163">However, an open generic type cannot be passed as a parameter to the `KnownTypeAttribute` attribute.</span></span>  
  
 <span data-ttu-id="fa324-164">Эту проблему можно решить с помощью альтернативного механизма: напишите метод, возвращающий типы, которые следует добавить в коллекцию известных типов.</span><span class="sxs-lookup"><span data-stu-id="fa324-164">This problem can be solved by using an alternative mechanism: Write a method that returns a list of types to add to the known types collection.</span></span> <span data-ttu-id="fa324-165">После этого имя метода задается в качестве строкового аргумента атрибута `KnownTypeAttribute` с некоторыми ограничениями.</span><span class="sxs-lookup"><span data-stu-id="fa324-165">The name of the method is then specified as a string argument to the `KnownTypeAttribute` attribute due to some restrictions.</span></span>  
  
 <span data-ttu-id="fa324-166">Этот метод должен существовать в типе, к которому применяется атрибут `KnownTypeAttribute` , должен быть статическим, не должен принимать параметров и должен возвращать объект, который можно присвоить интерфейсу <xref:System.Collections.IEnumerable> типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="fa324-166">The method must exist on the type to which the `KnownTypeAttribute` attribute is applied, must be static, must accept no parameters, and must return an object that can be assigned to <xref:System.Collections.IEnumerable> of <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="fa324-167">Нельзя объединять атрибут `KnownTypeAttribute` с именем метода и атрибутами `KnownTypeAttribute` с реальными типами в рамках одного типа.</span><span class="sxs-lookup"><span data-stu-id="fa324-167">You cannot combine the `KnownTypeAttribute` attribute with a method name and `KnownTypeAttribute` attributes with actual types on the same type.</span></span> <span data-ttu-id="fa324-168">Более того, нельзя применять более одного атрибута `KnownTypeAttribute` с именем метода к одному и тому же типу.</span><span class="sxs-lookup"><span data-stu-id="fa324-168">Furthermore, you cannot apply more than one `KnownTypeAttribute` with a method name to the same type.</span></span>  
  
 <span data-ttu-id="fa324-169">См. приведенный ниже класс.</span><span class="sxs-lookup"><span data-stu-id="fa324-169">See the following class.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#9)]
 [!code-vb[C_KnownTypeAttribute#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#9)]  
  
 <span data-ttu-id="fa324-170">Поле `theDrawing` содержит экземпляры универсального класса `ColorDrawing` и универсального класса `BlackAndWhiteDrawing`, которые оба наследуют универсальному классу `Drawing`.</span><span class="sxs-lookup"><span data-stu-id="fa324-170">The `theDrawing` field contains instances of a generic class `ColorDrawing` and a generic class `BlackAndWhiteDrawing`, both of which inherit from a generic class `Drawing`.</span></span> <span data-ttu-id="fa324-171">В список известных типов должны быть добавлены оба типа, но следующий синтаксис является недопустимым для атрибутов.</span><span class="sxs-lookup"><span data-stu-id="fa324-171">Normally, both must be added to known types, but the following is not valid syntax for attributes.</span></span>  
  
```csharp  
// Invalid syntax for attributes:  
// [KnownType(typeof(ColorDrawing<T>))]  
// [KnownType(typeof(BlackAndWhiteDrawing<T>))]  
```  
  
```vb  
' Invalid syntax for attributes:  
' <KnownType(GetType(ColorDrawing(Of T))), _  
' KnownType(GetType(BlackAndWhiteDrawing(Of T)))>  
```  
  
 <span data-ttu-id="fa324-172">Поэтому необходимо создать метод, который бы возвращал эти типы.</span><span class="sxs-lookup"><span data-stu-id="fa324-172">Thus, a method must be created to return these types.</span></span> <span data-ttu-id="fa324-173">В следующем примере кода показано, как правильно описать этот тип.</span><span class="sxs-lookup"><span data-stu-id="fa324-173">The correct way to write this type, then, is shown in the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#10)]
 [!code-vb[C_KnownTypeAttribute#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#10)]  
  
## <a name="additional-ways-to-add-known-types"></a><span data-ttu-id="fa324-174">Дополнительные способы добавления известных типов</span><span class="sxs-lookup"><span data-stu-id="fa324-174">Additional Ways to Add Known Types</span></span>  
 <span data-ttu-id="fa324-175">Кроме того, известные типы можно добавлять с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa324-175">Additionally, known types can be added through a configuration file.</span></span> <span data-ttu-id="fa324-176">Это полезно в том случае, если нет возможности управлять типом, требующим известных типов для правильной десериализации применения списка, например при использовании сторонних библиотек с Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fa324-176">This is useful when you do not control the type that requires known types for proper deserialization, such as when using third-party type libraries with Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="fa324-177">В следующем файле конфигурации показано, как задать известный тип в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa324-177">The following configuration file shows how to specify a known type in a configuration file.</span></span>  
  
 `<configuration>`  
  
 `<system.runtime.serialization>`  
  
 `<dataContractSerializer>`  
  
 `<declaredTypes>`  
  
 `<add type="MyCompany.Library.Shape,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL">`  
  
 `<knownType type="MyCompany.Library.Circle,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL"/>`  
  
 `</add>`  
  
 `</declaredTypes>`  
  
 `</dataContractSerializer>`  
  
 `</system.runtime.serialization>`  
  
 `</configuration>`  
  
 <span data-ttu-id="fa324-178">В приведенном выше файле конфигурации объявлено, что тип контракта данных `MyCompany.Library.Shape` должен содержать известный тип `MyCompany.Library.Circle` .</span><span class="sxs-lookup"><span data-stu-id="fa324-178">In the preceding configuration file a data contract type called `MyCompany.Library.Shape` is declared to have `MyCompany.Library.Circle` as a known type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa324-179">См. также</span><span class="sxs-lookup"><span data-stu-id="fa324-179">See Also</span></span>  
 <xref:System.Runtime.Serialization.KnownTypeAttribute>  
 <xref:System.Collections.Hashtable>  
 <xref:System.Object>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A>  
 [<span data-ttu-id="fa324-180">Известные типы</span><span class="sxs-lookup"><span data-stu-id="fa324-180">Known Types</span></span>](../../../../docs/framework/wcf/samples/known-types.md)  
 [<span data-ttu-id="fa324-181">Эквивалентность контрактов данных</span><span class="sxs-lookup"><span data-stu-id="fa324-181">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="fa324-182">Разработка контрактов службы</span><span class="sxs-lookup"><span data-stu-id="fa324-182">Designing Service Contracts</span></span>](../../../../docs/framework/wcf/designing-service-contracts.md)
