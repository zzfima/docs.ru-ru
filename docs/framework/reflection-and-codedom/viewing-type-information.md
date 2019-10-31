---
title: Просмотр сведений о типах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- types, viewing type information
- Type object
- viewing type information
- reflection, viewing type information
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
ms.openlocfilehash: bf119ff547df59cd369d688fd81ab058893614f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130015"
---
# <a name="viewing-type-information"></a>Просмотр сведений о типах
Класс <xref:System.Type?displayProperty=nameWithType> является центральной частью отражения. Среда CLR создает объект **Type** для загруженного типа, когда он запрашивается отражением. Используя методы, поля, свойства и вложенные классы объекта **Type**, можно получить полные сведения об этом типе.  
  
 Используйте <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> или <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> для получения объектов **Type** из сборок, которые не были загружены, передавая имя необходимого типа или типов. Используйте <xref:System.Type.GetType%2A?displayProperty=nameWithType> для получения объектов **Type** из уже загруженной сборки. Используйте <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> и <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> для получения объектов **Type** модуля.  
  
> [!NOTE]
> Если следует проверить универсальные типы и методы и управлять ими, ознакомьтесь с дополнительными сведениями, приведенными в разделах [Отражение и универсальные типы](reflection-and-generic-types.md) и [Практическое руководство. Изучение универсальных типов и создание их экземпляров при помощи отражения](how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 В приведенном ниже примере показан синтаксис для получения объекта <xref:System.Reflection.Assembly> и модуля сборки.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 В приведенном ниже примере показано, как получать объекты **Type** из загруженной сборки.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 После получения объекта **Type** сведения о членах этого типа можно получить разными способами. Например, можно узнать о всех членах этого типа посредством вызова метода <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>, который получает массив объектов <xref:System.Reflection.MemberInfo>, где описываются все члены текущего типа.  
  
 Методы класса **Type** можно также использовать для получения сведений об одном конструкторе или нескольких конструкторах, методах, событиях, полях или свойствах, заданных по имени. Например, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> инкапсулирует определенный конструктор текущего класса.  
  
 Если имеется объект **Type**, вы можете использовать свойство <xref:System.Type.Module%2A?displayProperty=nameWithType> для получения объекта, который инкапсулирует модуль, содержащий этот тип. Используйте свойство <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> для обнаружения объекта, который инкапсулирует сборку, содержащую модуль. Вы можете напрямую получить сборку, которая инкапсулирует тип, с помощью свойства <xref:System.Type.Assembly%2A?displayProperty=nameWithType>.  
  
## <a name="systemtype-and-constructorinfo"></a>System.Type и ConstructorInfo  
 В приведенном ниже примере показано, как получить список конструкторов класса, в этом случае для класса <xref:System.String>.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a>MemberInfo, MethodInfo, FieldInfo и PropertyInfo  
 Для получения сведений о методах, свойствах, событиях и полях типа используйте объекты <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> и <xref:System.Reflection.PropertyInfo>.  
  
 В приведенном ниже примере используется объект **MemberInfo** для вывода количества членов в классе **System.IO.File** и свойство <xref:System.Type.IsPublic%2A> для определения степени доступности этого класса.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 В приведенном ниже примере анализируется тип указанного члена. Выполняется отражение члена класса **MemberInfo** и выводятся сведения о его типе.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 В приведенном ниже примере используются все классы отражения **\*Info** вместе с классом <xref:System.Reflection.BindingFlags> для получения сведений о всех членах (конструкторах, полях, свойствах, событиях и методах) указанного класса, причем статические члены выводятся отдельно от членов экземпляров.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.BindingFlags>
- <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>
- <xref:System.Type.GetFields%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Reflection.MemberInfo>
- <xref:System.Reflection.ConstructorInfo>
- <xref:System.Reflection.MethodInfo>
- <xref:System.Reflection.FieldInfo>
- <xref:System.Reflection.EventInfo>
- <xref:System.Reflection.ParameterInfo>
- [Отражение и универсальные типы](reflection-and-generic-types.md)
