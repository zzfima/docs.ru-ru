---
title: Пошаговое руководство. Выполнение запросов со связями (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: a7da43e3-769f-4e07-bcd6-552b8bde66f4
ms.openlocfilehash: 3164656bb183e7773b098cab79d8fe5e0dc5de34
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792142"
---
# <a name="walkthrough-querying-across-relationships-visual-basic"></a>Пошаговое руководство. Выполнение запросов со связями (Visual Basic)
В этом пошаговом руководстве [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] демонстрируется использование *ассоциаций* для представления связей внешнего ключа в базе данных.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Это пошаговое руководство было написано с помощью параметров разработки Visual Basic.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Необходимо выполнить [пошаговое руководство. Простая объектная модель и запрос (Visual Basic](walkthrough-simple-object-model-and-query-visual-basic.md)). На этом пошаговом руководстве основано руководство, описываемое в данном разделе. В частности на компьютере должен иметься файл northwnd.mdf в папке c:\linqtest.  
  
## <a name="overview"></a>Обзор  
 Данное пошаговое руководство состоит из трех основных задач.  
  
- Добавление класса сущности, который представляет таблицу "Orders" в базе данных "Northwind".  
  
- Добавление примечаний к классу `Customer`, чтобы расширить связи между классами `Customer` и `Order`.  
  
- Создание и выполнение запроса для тестирования процесса получения сведений класса `Order` с помощью класса `Customer`.  
  
## <a name="mapping-relationships-across-tables"></a>Сопоставление связей между таблицами  
 После определения класса `Customer` создайте определение класса сущностей `Order`, включающее следующий код, который указывает, что свойство `Orders.Customer` связано как внешний ключ со свойством `Customers.CustomerID`.  
  
#### <a name="to-add-the-order-entity-class"></a>Добавление класса сущностей "Order"  
  
- Введите или вставьте следующий код после определения класса `Customer`.  
  
     [!code-vb[DLinqWalk2VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#1)]  
  
## <a name="annotating-the-customer-class"></a>Добавление примечаний к классу "Customer"  
 На этом этапе добавляются примечания к классу `Customer`, чтобы указать его связь с классом `Order`. (Это добавление не является обязательным, поскольку для создания связи достаточно создать определение связи в любом направлении. Однако добавление этого примечания позволит с легкостью переходить по объектам в любом направлении.)  
  
#### <a name="to-annotate-the-customer-class"></a>Добавление примечаний к классу "Customer"  
  
- Введите или вставьте следующий код в класс `Customer`.  
  
     [!code-vb[DLinqWalk2VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a>Создание и выполнение запроса в рамках связи "Customer-Order"  
 Теперь можно получить доступ к объектам `Order` непосредственно из объектов `Customer` или в обратном направлении. Явное *соединение* между клиентами и заказами не требуется.  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a>Получение доступа к объектам "Order" с помощью объектов "Customer"  
  
1. Измените метод `Sub Main` посредством ввода или вставки в метод следующего кода:  
  
     [!code-vb[DLinqWalk2VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#3)]  
  
2. Нажмите клавишу F5, чтобы начать отладку приложения.  
  
     В окне сообщения отобразятся два имени, и в окне "Консоль" появится созданный код SQL.  
  
3. Закройте окно сообщения, чтобы остановить отладку.  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a>Создание строго типизированного представления базы данных  
 Общая процедура становится гораздо проще, если в начале использовать строго типизированное представление базы данных. Задавая строгую типизацию объекта <xref:System.Data.Linq.DataContext>, можно избежать вызовов метода <xref:System.Data.Linq.DataContext.GetTable%2A>. Строго типизированные таблицы можно использовать в запросах только при использовании строго типизированного объекта <xref:System.Data.Linq.DataContext>.  
  
 В представленных ниже шагах создается объект `Customers` в качестве строго типизированной таблицы, которая сопоставляется с таблицей "Customers" в базе данных.  
  
#### <a name="to-strongly-type-the-datacontext-object"></a>Установка строгой типизации объекта "DataContext"  
  
1. Добавьте следующий код непосредственно перед объявлением класса `Customer`.  
  
     [!code-vb[DLinqWalk2VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#4)]  
  
2. Измените метод `Sub Main`, чтобы использовать строго типизированный объект <xref:System.Data.Linq.DataContext>, как показано ниже:  
  
     [!code-vb[DLinqWalk2VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#5)]  
  
3. Нажмите клавишу F5, чтобы начать отладку приложения.  
  
     В окне «Консоль"» отобразится следующее.  
  
     `ID=WHITC`  
  
4. Чтобы закрыть приложение, в окне "Консоль" нажмите клавишу ВВОД.  
  
5. Чтобы сохранить это приложение, в меню **файл** выберите команду **сохранить все** .  
  
## <a name="next-steps"></a>Следующие шаги  
 Следующее пошаговое[руководство (пошаговое руководство. Обработка данных (Visual Basic)](walkthrough-manipulating-data-visual-basic.md)) демонстрирует управление данными. Для этого пошагового руководства не требуется сохранять два пошаговых руководства, которые уже выполнены в этой серии.  
  
## <a name="see-also"></a>См. также

- [Обучение с использованием пошаговых руководств](learning-by-walkthroughs.md)
