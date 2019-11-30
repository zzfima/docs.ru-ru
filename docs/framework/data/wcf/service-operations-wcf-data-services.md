---
title: Операции служб (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: 583a690a-e60f-4990-8991-d6efce069d76
ms.openlocfilehash: c254a7362c7bc28f4b38fc0189ae0ea763bc90cc
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568848"
---
# <a name="service-operations-wcf-data-services"></a>Операции служб (службы данных WCF)

WCF Data Services позволяет определять операции службы в службе данных для предоставления методов на сервере. Как и остальные ресурсы службы данных, операции службы адресуются с помощью URI. Операции службы позволяют предоставлять бизнес-логику службы данных, например реализовывать логику проверки, применять правила безопасности на основе ролей и предоставлять специализированные возможности запросов. Операции службы представляют собой методы, добавленные в класс службы данных, производный от класса <xref:System.Data.Services.DataService%601>. Как и остальные ресурсы службы данных, методы операций службы поддерживают передачу параметров. Например, следующий универсальный код ресурса (URI) операции службы ( [на основе службы данных быстрого](quickstart-wcf-data-services.md) запуска) передает значение `London` в параметр `city`:

```http
http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'
```

Определение этой операции службы выглядит следующим образом:

[!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
[!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

Свойство <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> класса <xref:System.Data.Services.DataService%601> можно использовать для непосредственного обращения к источнику данных при работе со службой данных. Дополнительные сведения см. [в разделе инструкции. Определение операции службы](how-to-define-a-service-operation-wcf-data-services.md).

Сведения о вызове операции службы из клиентского приложения .NET Framework см. в разделе [вызов операций службы](calling-service-operations-wcf-data-services.md).

## <a name="service-operation-requirements"></a>Требования к операциям службы

Следующие требования применяются при определении операций службы в службе данных. Если метод не соответствует этим требованиям, то не предоставляется в качестве операции службы для службы данных.

- Операция должна быть методом публичного экземпляра, являющимся элементом класса службы данных.

- Метод операции может принимать только входные параметры. Данные, отправленные в тексте сообщения, недоступны для службы данных.

- Если параметры определены, каждый параметр должен иметь примитивный тип. Любые данные, не являющееся типом-примитивом, должны быть сериализованы и переданы в строковый параметр.

- Метод должен возвращать одно из следующих значений:

  - `void` (`Nothing` в Visual Basic).

  - <xref:System.Collections.Generic.IEnumerable%601>

  - <xref:System.Linq.IQueryable%601>

  - Тип сущности в модели данных, которую предоставляет служба данных.

  - Примитивный класс, такой как целое число или строка.

- Для поддержки параметров запросов, таких как сортировка, разбиение по страницам и фильтрация, методы операций службы должны возвращать класс <xref:System.Linq.IQueryable%601>. Запросы к операциям службы, включающие параметры запросов, не допускаются для операций, которые возвращают только интерфейс <xref:System.Collections.Generic.IEnumerable%601>.

- Для поддержки доступа к связанным сущностям с помощью навигационных свойств операция службы должна возвращать интерфейс <xref:System.Linq.IQueryable%601>.

- Метод должен сопровождаться атрибутом `[WebGet]` или `[WebInvoke]`.

  - `[WebGet]` позволяет вызывать метод с помощью запроса GET.

  - `[WebInvoke(Method = "POST")]` позволяет вызывать метод с помощью запроса POST. Другие методы <xref:System.ServiceModel.Web.WebInvokeAttribute> не поддерживаются.

- Операция службы может сопровождаться атрибутом <xref:System.Data.Services.SingleResultAttribute>, который указывает, что возвращаемое из метода значение является отдельной сущностью, а не коллекцией сущностей. Это различие определяет результирующую сериализацию ответа и способ представления обхода дополнительных навигационных свойств в URI. Например, при использовании сериализации AtomPub отдельный экземпляр типа ресурса представлен в качестве элемента entry, а набор экземпляров — в качестве элемента feed.

## <a name="addressing-service-operations"></a>Адресация операций службы

Адресовать операции службы можно, помещая имя метода в первый сегмент пути в URI. Например, следующий URI обращается к операции `GetOrdersByState`, которая возвращает коллекцию <xref:System.Linq.IQueryable%601> объектов `Orders`.

```http
http://localhost:12345/Northwind.svc/GetOrdersByState?state='CA'&includeItems=true
```

При вызове операции службы параметры предоставляются в качестве параметров запроса. Предыдущая операция службы принимает как строковый параметр `state`, так и логический параметр `includeItems`, который указывает, следует ли включить в ответ связанные объекты `Order_Detail`.

Ниже приведены допустимые типы возвращаемых значений для операции службы.

|Допустимые типы возвращаемых значений|Правила URI|
|------------------------|---------------|
|`void` (`Nothing` в Visual Basic).<br /><br /> \- или -<br /><br /> Типы сущностей<br /><br /> \- или -<br /><br /> Примитивные типы|URI должен содержать один сегмент пути, представляющий собой имя операции службы. Параметры запросов не допускаются.|
|<xref:System.Collections.Generic.IEnumerable%601>|URI должен содержать один сегмент пути, представляющий собой имя операции службы. Поскольку результат имеет тип, отличный от <xref:System.Linq.IQueryable%601>, параметры запросов не допускаются.|
|<xref:System.Linq.IQueryable%601>|Допускаются сегменты пути запроса в дополнение к имени операции службы. Параметры запросов также допускаются.|

Дополнительные сегменты пути или параметры запросов добавляются в URI в зависимости от типа возвращаемого значения операции службы. Например, следующий URI обращается к операции `GetOrdersByCity`, которая возвращает коллекцию <xref:System.Linq.IQueryable%601> объектов `Orders`, упорядоченных по значению `RequiredDate` в убывающем порядке, вместе со связанными объектами `Order_Details`:

```http
http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc
```

## <a name="service-operations-access-control"></a>Управление доступом к операциям службы

Управление общей видимостью операций службы осуществляется с помощью метода <xref:System.Data.Services.IDataServiceConfiguration.SetServiceOperationAccessRule%2A> класса <xref:System.Data.Services.IDataServiceConfiguration> в основном так же, как происходит управление видимостью набора сущностей с помощью метода <xref:System.Data.Services.IDataServiceConfiguration.SetEntitySetAccessRule%2A>. Например, в следующей строке кода определения службы данных включается доступ к операции службы `CustomersByCity`.

[!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
[!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

> [!NOTE]
> Если операция службы имеет тип возвращаемого значения, скрытый путем ограничения доступа к базовым наборам сущностей, операция службы не будет доступна клиентским приложениям.

Дополнительные сведения см. [в разделе инструкции. Определение операции службы](how-to-define-a-service-operation-wcf-data-services.md).

## <a name="raising-exceptions"></a>Вызов исключений

Рекомендуется использовать класс <xref:System.Data.Services.DataServiceException> всякий раз, когда нужно вызывать исключение при выполнении службы данных. Это необходимо потому, что среде выполнения службы данных известно, как правильно сопоставить свойства этого объекта исключения с ответным сообщением HTTP. При вызове <xref:System.Data.Services.DataServiceException> в операции службы возвращаемое исключение упаковывается в <xref:System.Reflection.TargetInvocationException>. Чтобы вернуть базовое <xref:System.Data.Services.DataServiceException> без включения <xref:System.Reflection.TargetInvocationException>, необходимо переопределить метод <xref:System.Data.Services.DataService%601.HandleException%2A> в <xref:System.Data.Services.DataService%601>, извлечь <xref:System.Data.Services.DataServiceException> из <xref:System.Reflection.TargetInvocationException> и возвратить его в качестве ошибки верхнего уровня, как показано в следующем примере:

[!code-csharp[Astoria Northwind Service#HandleExceptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#handleexceptions)]
[!code-vb[Astoria Northwind Service#HandleExceptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#handleexceptions)]

## <a name="see-also"></a>См. также:

- [Перехватчики](interceptors-wcf-data-services.md)
