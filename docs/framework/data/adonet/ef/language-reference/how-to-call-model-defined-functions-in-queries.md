---
title: "Как вызывать определяемые моделью функции в запросах | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как вызывать определяемые моделью функции в запросах
В этом разделе описаны процедуры вызова функций, определенные в концептуальной модели, из запросов [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
 Приведенная ниже процедура обеспечивает высокоуровневую структуру для вызова функции, определяемой моделью, из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  В следующем примере подробно описаны шаги данной процедуры.  Для этой процедуры предполагается, что функция была определена в концептуальной модели.  Для получения дополнительной информации см. [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ru-ru/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### Вызов функции, определенной в концептуальной модели  
  
1.  Добавьте в приложение метод среды CLR, который сопоставляется с функцией, определенной в концептуальной модели.  Для сопоставления метода к нему необходимо применить атрибут <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.  При разрешении имени функции для LINQ учитывается регистр.  
  
2.  Вызовите функцию в запросе [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
## Пример  
 В следующем примере показано, как вызвать функцию, определенную в концептуальной модели, из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  В этом примере используется модель School.  Дополнительные сведения о модели School см. в разделах [Creating the School Sample Database](http://msdn.microsoft.com/ru-ru/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) и [Generating the School .edmx File](http://msdn.microsoft.com/ru-ru/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 В следующей концептуальной модели функция возвращает сведения о количестве лет, истекших с момента приема инструктора на работу.  \(Сведения о добавлении функции к концептуальной модели см. в разделе [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ru-ru/0dad7b8b-58f6-4271-b238-f34810d68e5f).\)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/obj/debug/edmxresourcestoembed/school.csdl#1)]  
  
## Пример  
 Затем добавьте в приложение следующий метод и с помощью атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> сопоставьте его с функцией концептуальной модели:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## Пример  
 Теперь можно вызвать функцию концептуальной модели из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  Следующий код вызывает метод, чтобы отобразить всех инструкторов, которые были приняты на работу более десяти лет назад:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## См. также  
 [.edmx File Overview](http://msdn.microsoft.com/ru-ru/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)   
 [Вызов функций в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)   
 [Как вызывать функции, определяемые в модели, в качестве методов объекта.](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)