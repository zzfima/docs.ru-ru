---
title: "Viewing Type Information | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "types, viewing type information"
  - "Type object"
  - "viewing type information"
  - "reflection, viewing type information"
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Viewing Type Information
Класс <xref:System.Type?displayProperty=fullName> является центральной частью отражения.  Среда CLR создает объект **Type** для загруженного типа, когда он запрашивается отражением.  Используя методы, поля, свойства и вложенные классы объекта **Type**, можно получить полные сведения об этом типе.  
  
 Используйте перегрузку <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> или метод <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> для получения объектов **Type** из сборок, которые не были загружены, передавая имя необходимого типа или типов.  Используйте перегрузку <xref:System.Type.GetType%2A?displayProperty=fullName> для получения объектов **Type** из уже загруженной сборки.  Используйте перегрузку <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName> и метод <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName> для получения объектов модуля **Type**.  
  
> [!NOTE]
>  Если планируется выполнение проверок и управление универсальными типами и методами, рекомендуется ознакомиться с дополнительными сведениями, приведенными в разделах [Reflection and Generic Types](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md) и [How to: Examine and Instantiate Generic Types with Reflection](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 В следующем примере показан синтаксис для получения объекта <xref:System.Reflection.Assembly> и модуля сборки.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 В следующем примере показано, как получать объекты **Type** из загруженной сборки.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 После получения объекта **Type** сведения об элементах этого типа можно получить разными способами.  Например, можно узнать обо всех элементах этого типа посредством вызова метода <xref:System.Type.GetMembers%2A?displayProperty=fullName>, который получит массив объектов <xref:System.Reflection.MemberInfo>, где будут описаны все элементы текущего типа.  
  
 Можно также использовать методы класса **Type** для получения сведений об одном или нескольких конструкторах, методах, событиях, полях или свойствах, заданных по имени.  Например, <xref:System.Type.GetConstructor%2A?displayProperty=fullName> инкапсулирует определенный конструктор текущего класса.  
  
 Если известен **Type**, можно использовать свойство <xref:System.Type.Module%2A?displayProperty=fullName> для получения объекта, который инкапсулирует модуль, содержащий этот тип.  Используйте свойство <xref:System.Reflection.Module.Assembly%2A?displayProperty=fullName> для обнаружения объекта, который инкапсулирует сборку, содержащую модуль.  Можно напрямую получить сборку, которая инкапсулирует тип, посредством использования свойства <xref:System.Type.Assembly%2A?displayProperty=fullName>.  
  
## System.Type и ConstructorInfo  
 В следующем примере показано, как отображать список конструкторов класса, в этом случае, для класса <xref:System.String>.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## MemberInfo, MethodInfo, FieldInfo и PropertyInfo  
 Получение сведений о методах, свойствах, событиях и полях типа с помощью объектов <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> и <xref:System.Reflection.PropertyInfo>.  
  
 В следующем примере используются объект**MemberInfo** для вывода количества элементов в классе **System.IO.File**  и свойство [System.Type.IsPublic](frlrfSystemTypeClassIsPublicTopic) для определения степени доступности этого класса.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 В следующем примере анализируется тип указанного элемента.  Выполняется отражение элемента класса **MemberInfo** и выводятся сведения о его типе.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 В следующем примере используются все классы отражения **\*Info** вместе с классом <xref:System.Reflection.BindingFlags> для получения сведений о всех элементах \(конструкторах, полях, свойствах, событиях и методах\) указанного класса, причем статические элементы выводятся отдельно от элементов экземпляров.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## См. также  
 <xref:System.Reflection.BindingFlags>   
 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.GetMembers%2A?displayProperty=fullName>   
 <xref:System.Type.GetFields%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Reflection.MemberInfo>   
 <xref:System.Reflection.ConstructorInfo>   
 <xref:System.Reflection.MethodInfo>   
 <xref:System.Reflection.FieldInfo>   
 <xref:System.Reflection.EventInfo>   
 <xref:System.Reflection.ParameterInfo>   
 [Reflection and Generic Types](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)