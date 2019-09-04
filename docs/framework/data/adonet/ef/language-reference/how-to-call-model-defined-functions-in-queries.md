---
title: Практическое руководство. Вызов определенных моделью функций в запросах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 33f26896dd0d4ff08beb4a011fa6bd468cba7207
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250760"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Практическое руководство. Вызов определенных моделью функций в запросах
В этом разделе описывается вызов функций, определенных в концептуальной модели, из запросов LINQ to Entities.  
  
 В приведенной ниже процедуре представлен общий обзор вызова определяемой моделью функции из LINQ to Entities запроса. В следующем примере подробно описаны шаги данной процедуры. Для этой процедуры предполагается, что функция была определена в концептуальной модели. Дополнительные сведения см. в разделе [Практическое руководство. Определите пользовательские функции в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>Вызов функции, определенной в концептуальной модели  
  
1. Добавьте в приложение метод среды CLR, который сопоставляется с функцией, определенной в концептуальной модели. Для сопоставления метода к нему необходимо применить атрибут <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно. При разрешении имени функции для LINQ учитывается регистр.  
  
2. Вызовите функцию в запросе LINQ to Entities.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как вызвать функцию, определенную в концептуальной модели, из запроса LINQ to Entities. В этом примере используется модель School. Сведения о модели School см. в разделе [Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) и [Создание файла School. EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).  
  
 В следующей концептуальной модели функция возвращает сведения о количестве лет, истекших с момента приема инструктора на работу. Дополнительные сведения о добавлении функции в концептуальную модель см. в [разделе как Определите пользовательские функции в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Пример  
 Затем добавьте в приложение следующий метод и с помощью атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> сопоставьте его с функцией концептуальной модели:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Пример  
 Теперь можно вызвать функцию концептуальной модели из LINQ to Entities запроса. Следующий код вызывает метод, чтобы отобразить всех инструкторов, которые были приняты на работу более десяти лет назад:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о файле EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Запросы в LINQ to Entities](queries-in-linq-to-entities.md)
- [Вызов функций в запросах LINQ to Entities](calling-functions-in-linq-to-entities-queries.md)
- [Практическое руководство. Вызов определяемых моделью функций в качестве методов объекта](how-to-call-model-defined-functions-as-object-methods.md)
