---
title: "Как вызывать функции, определяемые в модели, в качестве методов объекта. | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как вызывать функции, определяемые в модели, в качестве методов объекта.
В данном разделе описывается, как вызвать определяемую в модели функцию в качестве метода для объекта <xref:System.Data.Objects.ObjectContext> или в качестве статического метода для пользовательского класса.  *Определяемая в модели функция* \- это функция, определяемая в концептуальной модели.  В данном разделе показываются процедуры вызова этих функций напрямую, а не с помощью запросов LINQ to Entities.  Сведения о вызове определяемых в модели функций в запросах LINQ to Entities см. в разделе [Как вызывать определяемые моделью функции в запросах](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md).  
  
 Если определяемая в модели функция вызвается как метод <xref:System.Data.Objects.ObjectContext> или как статический метод для пользовательского класса, в первую очередь необходимо сопоставить метод с определямой в модели функцией с <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  Если метод определяется для класса <xref:System.Data.Objects.ObjectContext>, то следует использовать свойство <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> для предоставления поставщика LINQ, однако, если статический метод определяется для пользовательского класса, то следует использовать свойство <xref:System.Linq.IQueryable.Provider%2A> для предоставления поставщика LINQ.  Дополнительные сведения см. в примерах, приведенных после указанных ниже процедур.  
  
 В следующих процедурах описываются высокоуровневые структуры для вызова определяемой в модели функции в качестве метода для объекта <xref:System.Data.Objects.ObjectContext> или в качестве статического метода для пользовательского класса.  В следующих примерах подробно описаны шаги данной процедуры.  Эта процедура предполагает, что функция была определена в концептуальной модели.  Для получения дополнительной информации см. [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ru-ru/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### Вызов определяемой в модели функции в качестве метода объекта ObjectContext  
  
1.  Добавьте исходный файл, чтобы расширить разделяемый класс, производный от класса <xref:System.Data.Objects.ObjectContext>, автоматически созданный средствами платформы Entity Framework.  Если заглушка CLR определена в отдельном исходном файле, это поможет предотвратить потерю изменений при повторном создании файла.  
  
2.  Добавьте к классу <xref:System.Data.Objects.ObjectContext> метод среды CLR, выполняющий следующие действия:  
  
    -   Устанавливает сопоставление с функцией, определяемой в концептуальной модели.  Для сопоставления метода к нему необходимо применить атрибут <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.  При разрешении имени функции для LINQ учитывается регистр.  
  
    -   Возвращает результаты метода <xref:System.Linq.IQueryProvider.Execute%2A>, возвращаемого свойством <xref:System.Data.Objects.ObjectContext.QueryProvider%2A>.  
  
3.  Вызовите метод в качестве элемента экземпляра класса <xref:System.Data.Objects.ObjectContext>.  
  
### Вызов определяемой в модели функции в качестве статического метода из пользовательского класса  
  
1.  Добавьте к приложению класс со статическим методом, выполняющий следующие действия:  
  
    -   Устанавливает сопоставление с функцией, определяемой в концептуальной модели.  Для сопоставления метода к нему необходимо применить атрибут <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.  
  
    -   Принимает аргумент <xref:System.Linq.IQueryable>.  
  
    -   Возвращает результаты метода <xref:System.Linq.IQueryProvider.Execute%2A>, возвращаемого свойством <xref:System.Linq.IQueryable.Provider%2A>.  
  
2.  Вызовите метод в качестве члена статического метода из пользовательского класса  
  
## Пример  
 **Вызов определяемой в модели функции в качестве метода объекта ObjectContext**  
  
 В приведенном ниже примере показано, как вызвать определяемую в модели функцию в качестве метода для объекта <xref:System.Data.Objects.ObjectContext>.  В примере используется [модель AdventureWorks Sales](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832).  
  
 Рассмотрите описанную ниже функцию концептуальной модели, возвращающую доход от указанного продукта.  \(Сведения о добавлении функции к концептуальной модели см. в разделе [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ru-ru/0dad7b8b-58f6-4271-b238-f34810d68e5f)\).  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#4)]
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#4)]
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  
  
## Пример  
 Следующий код добавляет метод к классу `AdventureWorksEntities`, который сопоставляется с функцией концептуальной модели, описанной выше.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## Пример  
 В следующем коде вызывается описанный выше метод для отображения дохода для указанного продукта:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## Пример  
 В приведенном ниже примере показано, как вызвать определяемую в модели функцию, возвращающую коллекцию \(как объект <xref:System.Linq.IQueryable%601>\).  Рассмотрите описанную ниже функцию концептуальной модели, возвращающую подробные сведения `SalesOrderDetails` для указанного идентификатора продукта.  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## Пример  
 Следующий код добавляет метод к классу `AdventureWorksEntities`, который сопоставляется с функцией концептуальной модели, описанной выше.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## Пример  
 Следующий код вызывает метод.  Обратите внимание, что возвращаемый запрос <xref:System.Linq.IQueryable%601> дорабатывается для возвращения линейных итогов для каждого `SalesOrderDetail`.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## Пример  
 **Вызов определяемой в модели функции в качестве статического метода из пользовательского класса**  
  
 В следующем примере показано, как вызвать определяемую в модели функцию в качестве статического метода из пользовательского класса.  В примере используется [модель AdventureWorks Sales](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832).  
  
> [!NOTE]
>  Если определяемая в модели функция вызывается как статический метод для пользовательского класса, эта функция должна принять коллекцию и вернуть результат статистической обработки значений из коллекции.  
  
 Рассмотрите описанную ниже функцию концептуальной модели, возвращающую доход от коллекции SalesOrderDetail.  \(Сведения о добавлении функции к концептуальной модели см. в разделе [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ru-ru/0dad7b8b-58f6-4271-b238-f34810d68e5f)\).  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#1)]
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/obj/x86/debug/edmxresourcestoembed/adventureworks.csdl#1)]
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]  
  
## Пример  
 Следующий код добавляет к приложению класс, содержащий статический метод, который сопоставляется с функцией концептуальной модели, описанной выше.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## Пример  
 В следующем коде вызывается описанный выше метод для отображения дохода для коллекции SalesOrderDetail:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## См. также  
 [.edmx File Overview](http://msdn.microsoft.com/ru-ru/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)   
 [Вызов функций в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)