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
# <a name="retrieving-information-stored-in-attributes"></a>Извлечение информации, сохраненной в атрибуте
Извлечение пользовательского атрибута — это простой процесс. Сначала объявите экземпляр атрибута, который требуется получить. Затем с помощью <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> метод для инициализации нового атрибута на значение атрибута, которые необходимо получить. После инициализации нового атрибута, можно просто использовать его свойства для получения значения.  
  
> [!IMPORTANT]
>  В этом разделе описывается получение атрибутов для кода, загруженного в контекст выполнения. Для получения атрибутов для кода, загруженного в контекст только для отражения, необходимо использовать <xref:System.Reflection.CustomAttributeData> класса, как показано в [как: загрузка сборки контекста, предназначенного](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
 В этом разделе описываются следующие способы извлечения атрибутов:  
  
-   [Извлечение единственного экземпляра атрибута](#cpconretrievingsingleinstanceofattribute)  
  
-   [Извлечение нескольких экземпляров атрибута, применяемых к одной области](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [Извлечение нескольких экземпляров атрибута, применяемых к разным областям](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a>Извлечение единственного экземпляра атрибута  
 В следующем примере `DeveloperAttribute` (как описано в предыдущем разделе) применяется к `MainApp` класса на уровне класса. `GetAttribute` Использует метод **GetCustomAttribute** для получения значений, хранящихся в `DeveloperAttribute` на уровне класса перед отображением их на консоль.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Эта программа выводит следующий текст при выполнении.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Если атрибут не найден, **GetCustomAttribute** инициализирует метод `MyAttribute` со значением null. В этом примере проверяется `MyAttribute` для такого экземпляра и уведомляет пользователя, если атрибут не найден. Если `DeveloperAttribute` не найден в области класса, выводит на консоль следующее сообщение.  
  
```  
The attribute was not found.   
```  
  
 Предполагается, что определения атрибута в текущем пространстве имен. Помните импортировать пространство имен, в котором хранится определение атрибута, если она не находится в текущем пространстве имен.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>Извлечение нескольких экземпляров атрибута, применяемых к одной области  
 В предыдущем примере, класс и определенный искомый атрибут передаются <xref:System.Attribute.GetCustomAttribute%2A>. Этот код работает хорошо, если только один экземпляр атрибута применяется на уровне класса. Тем не менее, если на том же уровне класса применяются несколько экземпляров атрибута **GetCustomAttribute** метод не сможет извлечь все данные. В случаях, когда несколько экземпляров одного атрибута применяются к той же области, можно использовать <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> поместить все экземпляры атрибута в массив. Например, если два вхождения `DeveloperAttribute` применяются на уровне класса того же класса `GetAttribute` метода можно изменить, чтобы отобразить сведения, найденные в обоих атрибутах. Помните, чтобы применить несколько атрибутов на одном уровне, атрибут должен быть определен с **AllowMultiple** свойство **true** в <xref:System.AttributeUsageAttribute>.  
  
 В следующем примере кода показано, как использовать **GetCustomAttributes** метод для создания массива, который ссылается на все экземпляры `DeveloperAttribute` в любом заданном классе. Значения всех атрибутов затем отображаются на консоль.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Если атрибуты не найдены, этот код уведомляет пользователя. В противном случае сведения, содержащиеся в обоих экземплярах `DeveloperAttribute` отображается.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>Извлечение нескольких экземпляров атрибута, применяемых к разным областям  
 <xref:System.Attribute.GetCustomAttributes%2A> И <xref:System.Attribute.GetCustomAttribute%2A> методы поиск по всему классу и не возвращают все экземпляры атрибута в этом классе. Вместо этого они ищут только один заданный метод или член одновременно. Если имеется класс с одним атрибутом, применяемый к каждому члену, и нужно извлечь значения всех атрибутов, применяемых к этим членам, необходимо указать каждый метод или член по отдельности в **GetCustomAttributes** и  **GetCustomAttribute**.  
  
 В следующем примере кода класс используется как параметр и выполняется поиск `DeveloperAttribute` (определенные ранее) на уровне класса и в каждом отдельном методе этого класса.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Если экземпляры `DeveloperAttribute` находятся на уровне метода или класса, `GetAttribute` метод сообщает пользователю, что атрибуты не найдены и отображает имя метода или класса, который не содержит атрибута. Если атрибут найден, `Name`, `Level`, и `Reviewed` поля отображаются на консоль.  
  
 Можно использовать члены <xref:System.Type> класса для получения отдельных методов и членов переданного класса. В этом примере сначала запрашивается **тип** объекта для получения данных атрибута на уровне класса. Затем он использует <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> для размещения экземпляров всех методов в массив <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> объекты для получения данных атрибута на уровне метода. Можно также использовать <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> метод для проверки атрибутов на уровне свойства или <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> для проверки атрибутов на уровне конструктора.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [Атрибуты](../../../docs/standard/attributes/index.md)
