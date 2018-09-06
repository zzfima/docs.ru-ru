---
title: Практическое руководство. Вызов определенных моделью функций в запросах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 2a20a2bb524c1ef9135b8b7187b2519088ddb762
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43778738"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Практическое руководство. Вызов определенных моделью функций в запросах
В этом разделе описаны процедуры вызова функций, определенные в концептуальной модели, из запросов [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
 Приведенная ниже процедура обеспечивает высокоуровневую структуру для вызова функции, определяемой моделью, из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. В следующем примере подробно описаны шаги данной процедуры. Для этой процедуры предполагается, что функция была определена в концептуальной модели. Дополнительные сведения см. в разделе [как: определения пользовательских функций в концептуальной модели](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>Вызов функции, определенной в концептуальной модели  
  
1.  Добавьте в приложение метод среды CLR, который сопоставляется с функцией, определенной в концептуальной модели. Для сопоставления метода к нему необходимо применить атрибут <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно. При разрешении имени функции для LINQ учитывается регистр.  
  
2.  Вызовите функцию в запросе [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как вызвать функцию, определенную в концептуальной модели, из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. В этом примере используется модель School. Сведения о модели School см. в разделе [Создание образца базы данных School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) и [Создание School EDMX-файл](https://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 В следующей концептуальной модели функция возвращает сведения о количестве лет, истекших с момента приема инструктора на работу. Сведения о добавлении функции к концептуальной модели, см. в разделе [как: определения пользовательских функций в концептуальной модели](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f).)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Пример  
 Затем добавьте в приложение следующий метод и с помощью атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> сопоставьте его с функцией концептуальной модели:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Пример  
 Теперь можно вызвать функцию концептуальной модели из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. Следующий код вызывает метод, чтобы отобразить всех инструкторов, которые были приняты на работу более десяти лет назад:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>См. также  
 [Обзор файла .edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Вызов функций в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Практическое руководство. Вызов определенных моделью функций как методов объектов](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
