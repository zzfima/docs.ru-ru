---
title: Извлечение информации, сохраненной в атрибуте
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
ms.openlocfilehash: 4f0f3555ae1ab7e662d5f88ac65739a7c791a964
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78158081"
---
# <a name="retrieving-information-stored-in-attributes"></a>Извлечение информации, сохраненной в атрибуте
Извлечение пользовательских атрибутов не представляет никакой сложности. Сначала объявите экземпляр атрибута, который вам нужно получить. Затем вызовите метод <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>, чтобы инициализировать новый атрибут тем значением, которое вы хотите получить. После инициализации нового атрибута обращайтесь к его свойствам, чтобы получить значения.  
  
> [!IMPORTANT]
> В этой статье объясняется, как можно получить настраиваемые атрибуты для кода, загруженного в контекст выполнения. Чтобы получить атрибуты для кода, загруженного в контекст только для отражения, необходимо использовать класс <xref:System.Reflection.CustomAttributeData>, как показано в статье [Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
 В этом разделе описываются следующие способы извлечения атрибутов.  
  
- [Извлечение единственного экземпляра атрибута](#cpconretrievingsingleinstanceofattribute)  
  
- [Извлечение нескольких экземпляров атрибута, применяемых к одной области](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
- [Извлечение нескольких экземпляров атрибута, применяемых к разным областям](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>
## <a name="retrieving-a-single-instance-of-an-attribute"></a>Извлечение единственного экземпляра атрибута  
 В следующем примере атрибут `DeveloperAttribute` (который описан в предыдущем разделе) применяется к классу `MainApp` на уровне класса. Метод `GetAttribute` использует **GetCustomAttribute** для получения значений, хранящихся в `DeveloperAttribute` на уровне класса, а затем выводит их в консоль.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Эта программа при выполнении выводит следующий текст.  
  
```console  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Если атрибут не найден, метод **GetCustomAttribute** инициализирует атрибут `MyAttribute` значением NULL. Этот пример проверяет наличие такого экземпляра в `MyAttribute` и уведомляет пользователя, если атрибут не найден. Если `DeveloperAttribute` не найден в области класса, на консоль выводится следующее сообщение.  
  
```console  
The attribute was not found.
```  
  
 В этом примере предполагается, что определения атрибута находится в текущем пространстве имен. Не забудьте импортировать пространство имен, в котором существует определение нужного атрибута, если это не текущее пространство имен.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>Извлечение нескольких экземпляров атрибута, применяемых к одной области  
 В предыдущем примере класс и искомый атрибут передаются в <xref:System.Attribute.GetCustomAttribute%2A>. Такой код будет работать правильно только в том случае, если на уровне класса применяется только один экземпляр нужного атрибута. Если же на одном уровне класса применяются несколько экземпляров атрибута, метод **GetCustomAttribute** не сможет извлечь все данные. Если несколько экземпляров одного атрибута применяются к одной области, вы можете поместить все экземпляры этого атрибута в массив с помощью <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>. Например, если на уровне класса применяются два вхождения `DeveloperAttribute`, метод `GetAttribute` можно изменить так, чтобы отобразить сведения из обоих атрибутов. Как вы помните, несколько атрибутов можно применить на одном уровне только в том случае, если в определении атрибута в <xref:System.AttributeUsageAttribute> свойство **AllowMultiple** имеет значение **true**.  
  
 В следующем примере кода показано, как использовать метод **GetCustomAttributes** для создания массива, который ссылается на все экземпляры `DeveloperAttribute` в любом заданном классе. Создав массив, метод выводит в консоль значения всех атрибутов.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Если атрибуты не найдены, код уведомляет об этом пользователя. В противном случае он выводит все сведения, содержащиеся в обоих экземплярах `DeveloperAttribute`.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>Извлечение нескольких экземпляров атрибута, применяемых к разным областям  
 Методы <xref:System.Attribute.GetCustomAttributes%2A> и <xref:System.Attribute.GetCustomAttribute%2A> не выполняют поиск по всему классу, чтобы вернуть все экземпляры атрибута в этом классе. Вместо этого они проверяют только один заданный метод или член за один вызов. Если у вас есть класс, в котором к каждому члену применен один и тот же атрибут, и вы хотите извлечь значения всех атрибутов, примененных к этим членам, к каждому методу и члену нужно обращаться по отдельности с помощью методов **GetCustomAttributes** и  **GetCustomAttribute**.  
  
 Следующий пример кода принимает класс в качестве параметра и выполняет в нем поиск атрибута `DeveloperAttribute` (определенного ранее) на уровне класса и в каждом отдельном методе этого класса.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Если на уровне методов и на уровне класса не обнаружен ни один экземпляр `DeveloperAttribute`, метод `GetAttribute` извещает пользователя о том, что атрибуты не найдены, а затем отображает имя метода и класса, в котором он искал атрибут. Если атрибут успешно найден, метод выводит в консоль поля `Name`, `Level` и `Reviewed`.  
  
 Вы можете использовать члены класса <xref:System.Type>, чтобы получить отдельные методы и члены переданного класса. Этот пример первым делом опрашивает объект **Type**, чтобы получить данные об атрибуте на уровне класса. После этого он выполняет <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>, чтобы поместить экземпляры всех методов в массив объектов <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> и получить данные об атрибуте на уровне методов. Вы также можете использовать метод <xref:System.Type.GetProperties%2A?displayProperty=nameWithType>, чтобы найти атрибуты на уровне свойств, или метод <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType>, чтобы найти атрибуты на уровне конструктора.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [Атрибуты](../../../docs/standard/attributes/index.md)
