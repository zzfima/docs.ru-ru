---
title: "Извлечение информации, сохраненной в атрибуте"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a><span data-ttu-id="27f23-102">Извлечение информации, сохраненной в атрибуте</span><span class="sxs-lookup"><span data-stu-id="27f23-102">Retrieving Information Stored in Attributes</span></span>
<span data-ttu-id="27f23-103">Извлечение пользовательского атрибута — это простой процесс.</span><span class="sxs-lookup"><span data-stu-id="27f23-103">Retrieving a custom attribute is a simple process.</span></span> <span data-ttu-id="27f23-104">Сначала объявите экземпляр атрибута, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="27f23-104">First, declare an instance of the attribute you want to retrieve.</span></span> <span data-ttu-id="27f23-105">Затем с помощью <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> метод для инициализации нового атрибута на значение атрибута, которые необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="27f23-105">Then, use the <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> method to initialize the new attribute to the value of the attribute you want to retrieve.</span></span> <span data-ttu-id="27f23-106">После инициализации нового атрибута, можно просто использовать его свойства для получения значения.</span><span class="sxs-lookup"><span data-stu-id="27f23-106">Once the new attribute is initialized, you simply use its properties to get the values.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27f23-107">В этом разделе описывается получение атрибутов для кода, загруженного в контекст выполнения.</span><span class="sxs-lookup"><span data-stu-id="27f23-107">This topic describes how to retrieve attributes for code loaded into the execution context.</span></span> <span data-ttu-id="27f23-108">Для получения атрибутов для кода, загруженного в контекст только для отражения, необходимо использовать <xref:System.Reflection.CustomAttributeData> класса, как показано в [как: загрузка сборки контекста, предназначенного](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="27f23-108">To retrieve attributes for code loaded into the reflection-only context, you must use the <xref:System.Reflection.CustomAttributeData> class, as shown in [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
 <span data-ttu-id="27f23-109">В этом разделе описываются следующие способы извлечения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="27f23-109">This section describes the following ways to retrieve attributes:</span></span>  
  
-   [<span data-ttu-id="27f23-110">Извлечение единственного экземпляра атрибута</span><span class="sxs-lookup"><span data-stu-id="27f23-110">Retrieving a single instance of an attribute</span></span>](#cpconretrievingsingleinstanceofattribute)  
  
-   [<span data-ttu-id="27f23-111">Извлечение нескольких экземпляров атрибута, применяемых к одной области</span><span class="sxs-lookup"><span data-stu-id="27f23-111">Retrieving multiple instances of an attribute applied to the same scope</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [<span data-ttu-id="27f23-112">Извлечение нескольких экземпляров атрибута, применяемых к разным областям</span><span class="sxs-lookup"><span data-stu-id="27f23-112">Retrieving multiple instances of an attribute applied to different scopes</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a><span data-ttu-id="27f23-113">Извлечение единственного экземпляра атрибута</span><span class="sxs-lookup"><span data-stu-id="27f23-113">Retrieving a Single Instance of an Attribute</span></span>  
 <span data-ttu-id="27f23-114">В следующем примере `DeveloperAttribute` (как описано в предыдущем разделе) применяется к `MainApp` класса на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="27f23-114">In the following example, the `DeveloperAttribute` (described in the previous section) is applied to the `MainApp` class on the class level.</span></span> <span data-ttu-id="27f23-115">`GetAttribute` Использует метод **GetCustomAttribute** для получения значений, хранящихся в `DeveloperAttribute` на уровне класса перед отображением их на консоль.</span><span class="sxs-lookup"><span data-stu-id="27f23-115">The `GetAttribute` method uses **GetCustomAttribute** to retrieve the values stored in `DeveloperAttribute` on the class level before displaying them to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 <span data-ttu-id="27f23-116">Эта программа выводит следующий текст при выполнении.</span><span class="sxs-lookup"><span data-stu-id="27f23-116">This program displays the following text when executed.</span></span>  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 <span data-ttu-id="27f23-117">Если атрибут не найден, **GetCustomAttribute** инициализирует метод `MyAttribute` со значением null.</span><span class="sxs-lookup"><span data-stu-id="27f23-117">If the attribute is not found, the **GetCustomAttribute** method initializes `MyAttribute` to a null value.</span></span> <span data-ttu-id="27f23-118">В этом примере проверяется `MyAttribute` для такого экземпляра и уведомляет пользователя, если атрибут не найден.</span><span class="sxs-lookup"><span data-stu-id="27f23-118">This example checks `MyAttribute` for such an instance and notifies the user if no attribute is found.</span></span> <span data-ttu-id="27f23-119">Если `DeveloperAttribute` не найден в области класса, выводит на консоль следующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="27f23-119">If the `DeveloperAttribute` is not found in the class scope, the following message displays to the console.</span></span>  
  
```  
The attribute was not found.   
```  
  
 <span data-ttu-id="27f23-120">Предполагается, что определения атрибута в текущем пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="27f23-120">This example assumes that the attribute definition is in the current namespace.</span></span> <span data-ttu-id="27f23-121">Помните импортировать пространство имен, в котором хранится определение атрибута, если она не находится в текущем пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="27f23-121">Remember to import the namespace in which the attribute definition resides if it is not in the current namespace.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a><span data-ttu-id="27f23-122">Извлечение нескольких экземпляров атрибута, применяемых к одной области</span><span class="sxs-lookup"><span data-stu-id="27f23-122">Retrieving Multiple Instances of an Attribute Applied to the Same Scope</span></span>  
 <span data-ttu-id="27f23-123">В предыдущем примере, класс и определенный искомый атрибут передаются <xref:System.Attribute.GetCustomAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="27f23-123">In the previous example, the class to inspect and the specific attribute to find are passed to <xref:System.Attribute.GetCustomAttribute%2A>.</span></span> <span data-ttu-id="27f23-124">Этот код работает хорошо, если только один экземпляр атрибута применяется на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="27f23-124">That code works well if only one instance of an attribute is applied on the class level.</span></span> <span data-ttu-id="27f23-125">Тем не менее, если на том же уровне класса применяются несколько экземпляров атрибута **GetCustomAttribute** метод не сможет извлечь все данные.</span><span class="sxs-lookup"><span data-stu-id="27f23-125">However, if multiple instances of an attribute are applied on the same class level, the **GetCustomAttribute** method does not retrieve all the information.</span></span> <span data-ttu-id="27f23-126">В случаях, когда несколько экземпляров одного атрибута применяются к той же области, можно использовать <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> поместить все экземпляры атрибута в массив.</span><span class="sxs-lookup"><span data-stu-id="27f23-126">In cases where multiple instances of the same attribute are applied to the same scope, you can use <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> to place all instances of an attribute into an array.</span></span> <span data-ttu-id="27f23-127">Например, если два вхождения `DeveloperAttribute` применяются на уровне класса того же класса `GetAttribute` метода можно изменить, чтобы отобразить сведения, найденные в обоих атрибутах.</span><span class="sxs-lookup"><span data-stu-id="27f23-127">For example, if two instances of `DeveloperAttribute` are applied on the class level of the same class, the `GetAttribute` method can be modified to display the information found in both attributes.</span></span> <span data-ttu-id="27f23-128">Помните, чтобы применить несколько атрибутов на одном уровне, атрибут должен быть определен с **AllowMultiple** свойство **true** в <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="27f23-128">Remember, to apply multiple attributes on the same level, the attribute must be defined with the **AllowMultiple** property set to **true** in the <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="27f23-129">В следующем примере кода показано, как использовать **GetCustomAttributes** метод для создания массива, который ссылается на все экземпляры `DeveloperAttribute` в любом заданном классе.</span><span class="sxs-lookup"><span data-stu-id="27f23-129">The following code example shows how to use the **GetCustomAttributes** method to create an array that references all instances of `DeveloperAttribute` in any given class.</span></span> <span data-ttu-id="27f23-130">Значения всех атрибутов затем отображаются на консоль.</span><span class="sxs-lookup"><span data-stu-id="27f23-130">The values of all attributes are then displayed to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 <span data-ttu-id="27f23-131">Если атрибуты не найдены, этот код уведомляет пользователя.</span><span class="sxs-lookup"><span data-stu-id="27f23-131">If no attributes are found, this code alerts the user.</span></span> <span data-ttu-id="27f23-132">В противном случае сведения, содержащиеся в обоих экземплярах `DeveloperAttribute` отображается.</span><span class="sxs-lookup"><span data-stu-id="27f23-132">Otherwise, the information contained in both instances of `DeveloperAttribute` is displayed.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a><span data-ttu-id="27f23-133">Извлечение нескольких экземпляров атрибута, применяемых к разным областям</span><span class="sxs-lookup"><span data-stu-id="27f23-133">Retrieving Multiple Instances of an Attribute Applied to Different Scopes</span></span>  
 <span data-ttu-id="27f23-134"><xref:System.Attribute.GetCustomAttributes%2A> И <xref:System.Attribute.GetCustomAttribute%2A> методы поиск по всему классу и не возвращают все экземпляры атрибута в этом классе.</span><span class="sxs-lookup"><span data-stu-id="27f23-134">The <xref:System.Attribute.GetCustomAttributes%2A> and <xref:System.Attribute.GetCustomAttribute%2A> methods do not search an entire class and return all instances of an attribute in that class.</span></span> <span data-ttu-id="27f23-135">Вместо этого они ищут только один заданный метод или член одновременно.</span><span class="sxs-lookup"><span data-stu-id="27f23-135">Rather, they search only one specified method or member at a time.</span></span> <span data-ttu-id="27f23-136">Если имеется класс с одним атрибутом, применяемый к каждому члену, и нужно извлечь значения всех атрибутов, применяемых к этим членам, необходимо указать каждый метод или член по отдельности в **GetCustomAttributes** и  **GetCustomAttribute**.</span><span class="sxs-lookup"><span data-stu-id="27f23-136">If you have a class with the same attribute applied to every member and you want to retrieve the values in all the attributes applied to those members, you must supply every method or member individually to **GetCustomAttributes** and **GetCustomAttribute**.</span></span>  
  
 <span data-ttu-id="27f23-137">В следующем примере кода класс используется как параметр и выполняется поиск `DeveloperAttribute` (определенные ранее) на уровне класса и в каждом отдельном методе этого класса.</span><span class="sxs-lookup"><span data-stu-id="27f23-137">The following code example takes a class as a parameter and searches for the `DeveloperAttribute` (defined previously) on the class level and on every individual method of that class.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 <span data-ttu-id="27f23-138">Если экземпляры `DeveloperAttribute` находятся на уровне метода или класса, `GetAttribute` метод сообщает пользователю, что атрибуты не найдены и отображает имя метода или класса, который не содержит атрибута.</span><span class="sxs-lookup"><span data-stu-id="27f23-138">If no instances of the `DeveloperAttribute` are found on the method level or class level, the `GetAttribute` method notifies the user that no attributes were found and displays the name of the method or class that does not contain the attribute.</span></span> <span data-ttu-id="27f23-139">Если атрибут найден, `Name`, `Level`, и `Reviewed` поля отображаются на консоль.</span><span class="sxs-lookup"><span data-stu-id="27f23-139">If an attribute is found, the `Name`, `Level`, and `Reviewed` fields are displayed to the console.</span></span>  
  
 <span data-ttu-id="27f23-140">Можно использовать члены <xref:System.Type> класса для получения отдельных методов и членов переданного класса.</span><span class="sxs-lookup"><span data-stu-id="27f23-140">You can use the members of the <xref:System.Type> class to get the individual methods and members in the passed class.</span></span> <span data-ttu-id="27f23-141">В этом примере сначала запрашивается **тип** объекта для получения данных атрибута на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="27f23-141">This example first queries the **Type** object to get attribute information for the class level.</span></span> <span data-ttu-id="27f23-142">Затем он использует <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> для размещения экземпляров всех методов в массив <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> объекты для получения данных атрибута на уровне метода.</span><span class="sxs-lookup"><span data-stu-id="27f23-142">Next, it uses <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> to place instances of all methods into an array of <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> objects to retrieve attribute information for the method level.</span></span> <span data-ttu-id="27f23-143">Можно также использовать <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> метод для проверки атрибутов на уровне свойства или <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> для проверки атрибутов на уровне конструктора.</span><span class="sxs-lookup"><span data-stu-id="27f23-143">You can also use the <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> method to check for attributes on the property level or <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> to check for attributes on the constructor level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f23-144">См. также</span><span class="sxs-lookup"><span data-stu-id="27f23-144">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="27f23-145">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27f23-145">Attributes</span></span>](../../../docs/standard/attributes/index.md)
