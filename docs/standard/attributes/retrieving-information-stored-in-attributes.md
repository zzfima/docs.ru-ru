---
title: "Извлечение информации, сохраненной в атрибуте | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "атрибуты [платформа .NET Framework], извлечение"
  - "несколько экземпляров атрибута"
  - "получение атрибутов"
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Извлечение информации, сохраненной в атрибуте
Извлечение пользовательского атрибута — достаточно простой процесс.  Сначала утвердите экземпляр атрибута, который необходимо извлечь.  Затем используйте метод <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName>, чтобы инициализировать новый атрибут для значения извлекаемого атрибута.  После инициализации нового атрибута для получения его значений просто используйте его свойства.  
  
> [!IMPORTANT]
>  В этом разделе описывается процесс извлечения атрибутов для кода, загруженного в контекст выполнения.  Чтобы извлечь атрибуты для кода, который загружен в контекст только для отражения, необходимо использовать класс <xref:System.Reflection.CustomAttributeData>, как показано в разделе [How to: Load Assemblies into the Reflection\-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
 В этом разделе описаны следующие способы извлечения атрибутов:  
  
-   [Извлечение единственного экземпляра атрибута](#cpconretrievingsingleinstanceofattribute)  
  
-   [Извлечение нескольких экземпляров атрибута, применяемых к одной области](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [Извлечение нескольких экземпляров атрибута, применяемых к разным областям](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## Извлечение единственного экземпляра атрибута  
 В следующем примере атрибут `DeveloperAttribute` \(описанный в предыдущем разделе\) применяется к классу `MainApp` на уровне класса.  Метод `GetAttribute` использует **GetCustomAttribute** для извлечения значений, хранящихся в `DeveloperAttribute` на уровне класса, перед отображением их на консоли.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 При выполнении этой программы выводится следующий текст.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Если атрибут не найден, то метод **GetCustomAttribute** инициализирует `MyAttribute` в значение null.  В этом примере выполняется проверка `MyAttribute` на существование такого экземпляра, и пользователь получает уведомление в случае, если атрибут не найден.  Если `DeveloperAttribute` не найден в области класса, то на консоль выводится следующее сообщение.  
  
```  
The attribute was not found.   
```  
  
 В этом примере предполагается, что атрибут определен в текущем пространстве имен.  Если пространство имен не текущее, то необходимо импортировать то пространство имен, в котором хранится определение данного атрибута.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## Извлечение нескольких экземпляров атрибута, применяемых к одной области  
 В предыдущем примере проверяемый класс и определенный искомый атрибут передаются в <xref:System.Attribute.GetCustomAttribute%2A>.  Этот код хорошо работает только в том случае, когда только один экземпляр атрибута применяется на уровне класса.  Однако если на уровне одного и того же класса применяются несколько экземпляров атрибута, то метод **GetCustomAttribute** не сможет извлечь все данные.  В случаях, когда несколько экземпляров одного атрибута применяются к одной области, можно использовать <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>, чтобы поместить все экземпляры атрибута в массив.  Например, если два экземпляра `DeveloperAttribute` применяются на уровне класса к одному и тому же классу, то метод `GetAttribute` может измениться таким образом, чтобы он отображал все данные, найденные в обоих атрибутах.  Помните, чтобы применить несколько атрибутов на одном уровне, атрибут должен быть определен со значением свойства **AllowMultiple** заданным **true** в <xref:System.AttributeUsageAttribute>.  
  
 В следующем примере показано, как использовать метод **GetCustomAttributes** для создания массива, ссылающегося на все экземпляры `DeveloperAttribute` в любом заданном классе.  Значения всех атрибутов затем отображаются на консоли.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Если атрибутов не найдено, то код уведомляет пользователя.  В противном случае отображаются сведения, содержащиеся в обоих экземплярах `DeveloperAttribute`.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## Извлечение нескольких экземпляров атрибута, применяемых к разным областям  
 Методы <xref:System.Attribute.GetCustomAttributes%2A> и <xref:System.Attribute.GetCustomAttribute%2A> не осуществляют поиск по всему классу и не возвращают все экземпляры атрибута в данном классе.  Они ищут только один заданный метод или член одновременно.  Если имеется класс с одним атрибутом, применяемый к каждому члену, и необходимо извлечь значения всех атрибутов, применяемых к этим членам, то следует поставлять по\-отдельности каждый метод или член в **GetCustomAttributes** и **GetCustomAttribute**.  
  
 В следующем примере кода класс используется как параметр и выполняется поиск атрибута `DeveloperAttribute`  \(определенного ранее\) на уровне класса и в каждом отдельном методе этого класса.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Если на уровне метода или класса экземпляры `DeveloperAttribute` не найдены, то метод `GetAttribute` уведомляет пользователя о том, что атрибуты не найдены, и отображает имя метода или класса, не содержащего данный атрибут.  Если атрибут найден, то поля `Name`, `Level` и `Reviewed` выводятся на консоль.  
  
 Члены класса <xref:System.Type> можно использовать для получения отдельных методов и членов переданного класса.  В этом примере для получения данных атрибута на уровне класса сначала запрашивается объект **Type**.  Затем он использует <xref:System.Type.GetMethods%2A?displayProperty=fullName> для расположения экземпляров всех методов в массиве объектов <xref:System.Reflection.MemberInfo?displayProperty=fullName> для получения сведений об атрибутах на уровне метода.  Можно также использовать метод <xref:System.Type.GetProperties%2A?displayProperty=fullName> для проверки атрибутов на уровне свойства или метод <xref:System.Type.GetConstructors%2A?displayProperty=fullName> для проверки атрибутов на уровне конструктора.  
  
## См. также  
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [Атрибуты](../../../docs/standard/attributes/index.md)