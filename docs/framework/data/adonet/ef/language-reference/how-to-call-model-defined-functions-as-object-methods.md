---
title: Практическое руководство. Вызов определенных моделью функций как методов объектов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
ms.openlocfilehash: 933baf39845caa2bc96828738d30f41613f69470
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304835"
---
# <a name="how-to-call-model-defined-functions-as-object-methods"></a>Практическое руководство. Вызов определенных моделью функций как методов объектов
В данном разделе описывается, как вызвать определяемую в модели функцию в качестве метода для объекта <xref:System.Data.Objects.ObjectContext> или в качестве статического метода для пользовательского класса. Объект *определяемой моделью функции* — это функция, которая определена в концептуальной модели. В данном разделе показываются процедуры вызова этих функций напрямую, а не с помощью запросов LINQ to Entities. Сведения о вызов определенных моделью функций в LINQ для запросов сущностей, см. в разделе [как: Вызов определенных моделью функций в запросах](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md).  
  
 Если определяемая в модели функция вызвается как метод <xref:System.Data.Objects.ObjectContext> или как статический метод для пользовательского класса, в первую очередь необходимо сопоставить метод с определямой в модели функцией с <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Если метод определяется для класса <xref:System.Data.Objects.ObjectContext>, то следует использовать свойство <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> для предоставления поставщика LINQ, однако, если статический метод определяется для пользовательского класса, то следует использовать свойство <xref:System.Linq.IQueryable.Provider%2A> для предоставления поставщика LINQ. Дополнительные сведения см. в примерах, приведенных после указанных ниже процедур.  
  
 В следующих процедурах описываются высокоуровневые структуры для вызова определяемой в модели функции в качестве метода для объекта <xref:System.Data.Objects.ObjectContext> или в качестве статического метода для пользовательского класса. В следующих примерах подробно описаны шаги данной процедуры. Эта процедура предполагает, что функция была определена в концептуальной модели. Дополнительные сведения см. в разделе [Как Определения пользовательских функций в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).  
  
### <a name="to-call-a-model-defined-function-as-a-method-on-an-objectcontext-object"></a>Вызов определяемой в модели функции в качестве метода объекта ObjectContext  
  
1. Добавьте исходный файл, чтобы расширить разделяемый класс, производный от класса <xref:System.Data.Objects.ObjectContext>, автоматически созданный средствами платформы Entity Framework. Если заглушка CLR определена в отдельном исходном файле, это поможет предотвратить потерю изменений при повторном создании файла.  
  
2. Добавьте к классу <xref:System.Data.Objects.ObjectContext> метод среды CLR, выполняющий следующие действия:  
  
    -   Устанавливает сопоставление с функцией, определяемой в концептуальной модели. Для сопоставления метода к нему необходимо применить атрибут <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно. При разрешении имени функции для LINQ учитывается регистр.  
  
    -   Возвращает результаты метода <xref:System.Linq.IQueryProvider.Execute%2A>, возвращаемого свойством <xref:System.Data.Objects.ObjectContext.QueryProvider%2A>.  
  
3. Вызовите метод в качестве элемента экземпляра класса <xref:System.Data.Objects.ObjectContext>.  
  
### <a name="to-call-a-model-defined-function-as-static-method-on-a-custom-class"></a>Вызов определяемой в модели функции в качестве статического метода из пользовательского класса  
  
1. Добавьте к приложению класс со статическим методом, выполняющий следующие действия:  
  
    -   Устанавливает сопоставление с функцией, определяемой в концептуальной модели. Для сопоставления метода к нему необходимо применить атрибут <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.  
  
    -   Принимает аргумент <xref:System.Linq.IQueryable>.  
  
    -   Возвращает результаты метода <xref:System.Linq.IQueryProvider.Execute%2A>, возвращаемого свойством <xref:System.Linq.IQueryable.Provider%2A>.  
  
2. Вызовите метод в качестве члена статического метода из пользовательского класса  
  
## <a name="example"></a>Пример  
 **Вызов определяемой моделью функции в качестве метода объекта ObjectContext**  
  
 В приведенном ниже примере показано, как вызвать определяемую в модели функцию в качестве метода для объекта <xref:System.Data.Objects.ObjectContext>. В примере используется [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).  
  
 Рассмотрите описанную ниже функцию концептуальной модели, возвращающую доход от указанного продукта. (Сведения о добавлении функции к концептуальной модели, см. в разделе [как: Определения пользовательских функций в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  

## <a name="example"></a>Пример  
 Следующий код добавляет метод к классу `AdventureWorksEntities`, который сопоставляется с функцией концептуальной модели, описанной выше.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## <a name="example"></a>Пример  
 В следующем коде вызывается описанный выше метод для отображения дохода для указанного продукта:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано, как вызвать определяемую в модели функцию, возвращающую коллекцию (как объект <xref:System.Linq.IQueryable%601>). Рассмотрите описанную ниже функцию концептуальной модели, возвращающую подробные сведения `SalesOrderDetails` для указанного идентификатора продукта.  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## <a name="example"></a>Пример  
 Следующий код добавляет метод к классу `AdventureWorksEntities`, который сопоставляется с функцией концептуальной модели, описанной выше.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## <a name="example"></a>Пример  
 Следующий код вызывает метод. Обратите внимание, что возвращаемый запрос <xref:System.Linq.IQueryable%601> дорабатывается для возвращения линейных итогов для каждого `SalesOrderDetail`.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## <a name="example"></a>Пример  
 **Вызов определяемой в модели функции в качестве статического метода из пользовательского класса**  
  
 В следующем примере показано, как вызвать определяемую в модели функцию в качестве статического метода из пользовательского класса. В примере используется [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).  
  
> [!NOTE]
>  Если определяемая в модели функция вызывается как статический метод для пользовательского класса, эта функция должна принять коллекцию и вернуть результат статистической обработки значений из коллекции.  
  
 Рассмотрите описанную ниже функцию концептуальной модели, возвращающую доход от коллекции SalesOrderDetail. (Сведения о добавлении функции к концептуальной модели, см. в разделе [как: Определения пользовательских функций в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).).  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]
  
## <a name="example"></a>Пример  
 Следующий код добавляет к приложению класс, содержащий статический метод, который сопоставляется с функцией концептуальной модели, описанной выше.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## <a name="example"></a>Пример  
 В следующем коде вызывается описанный выше метод для отображения дохода для коллекции SalesOrderDetail:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Обзор файла .edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
- [Вызов функций в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
