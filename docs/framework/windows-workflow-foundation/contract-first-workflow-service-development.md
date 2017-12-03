---
title: "Разработка службы рабочих процессов на основе контракта"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5dbaa7b-005f-4330-848d-58ac4f42f093
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c3d22c83f5fbc1144d139c9e7ba6a43137f6d144
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="contract-first-workflow-service-development"></a>Разработка службы рабочих процессов на основе контракта
Начиная с версии [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[wf](../../../includes/wf-md.md)] обеспечивает более качественную интеграцию между веб-службами и рабочими процессами с помощью средств разработки рабочего процесса на основе контракта (WCF). Средство разработки рабочих процессов на основе контракта позволяет создать контракт в Code First. Затем это средство автоматически создает в области элементов шаблон действия для каждой операции в контракте. В этом разделе содержатся общие сведения о том, как действия и свойства в службе рабочих процессов сопоставляются с атрибутами контракта службы. Пример с пошаговыми инструкциями создания рабочих процессов на основе контракта службы, в разделе [как: создание службы рабочего процесса, который использует существующий контракт службы](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).  
  
## <a name="in-this-topic"></a>Содержание раздела  
  
-   [Сопоставление атрибутов контракта службы с атрибутами рабочего процесса](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MappingAttributes)  
  
    -   [Атрибуты контракта службы](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ServiceContract)  
  
    -   [Атрибуты контракта операции](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#OperationContract)  
  
    -   [Атрибуты контракта сообщения](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MessageContract)  
  
    -   [Атрибуты контракта данных](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#DataContract)  
  
    -   [Атрибуты контракта ошибок](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#FaultContract)  
  
-   [Дополнительные сведения и сведения о реализации](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#AdditionalSupport)  
  
    -   [Неподдерживаемые возможности контракта службы](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
    -   [Создание настроенных действий обмена сообщениями](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ActivityGeneration)  
  
##  <a name="MappingAttributes"></a>Сопоставление атрибутов контракта службы с атрибутами рабочего процесса  
 Таблицы в следующих разделах показывают различные атрибуты и свойства WCF, а также как они сопоставляются с действиями по обмену сообщениями и их свойствами в рабочем процессе на основе контракта.  
  
-   [Атрибуты контракта службы](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ServiceContract)  
  
-   [Атрибуты контракта операции](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#OperationContract)  
  
-   [Атрибуты контракта сообщения](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MessageContract)  
  
-   [Атрибуты контракта данных](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#DataContract)  
  
-   [Атрибуты контракта ошибок](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#FaultContract)  
  
###  <a name="ServiceContract"></a>Атрибуты контракта службы  
  
|Имя свойства|Поддерживается|Описание|Проверка рабочего процесса|  
|-------------------|---------------|-----------------|-------------------|  
|CallbackContract|Нет|Возвращает или задает тип контракта обратного вызова, если контракт является дуплексным.|(не определено)|  
|ConfigurationName|Нет|Возвращает или задает имя, используемое для поиска службы в файле конфигурации приложения.|(не определено)|  
|HasProtectionLevel|Да|Возвращает значение, указывающее, присвоен ли участнику уровень защиты.|Свойство Receive.ProtectionLevel не должно иметь значение NULL.|  
|Имя|Да|Возвращает или задает имя для \<portType > элемент в языке описания веб-служб (WSDL).|Свойство Receive.ServiceContractName.LocalName должно согласовываться.|  
|Пространство имен|Да|Возвращает или задает пространство имен \<portType > элемент в языке описания веб-служб (WSDL).|Свойство Receive.ServiceContractName.NameSpace должно согласовываться.|  
|ProtectionLevel|Да|Указывает, должна ли привязка для контракта поддерживать значение свойства ProtectionLevel.|Свойство Receive.ProtectionLevel должно согласовываться.|  
|SessionMode|Нет|Возвращает или задает значение, указывающее, разрешены, запрещены или требуются ли сеансы.|(не определено)|  
|TypeId|Нет|В случае реализации в производном классе возвращает уникальный идентификатор для этого атрибута. (Наследуется от атрибута.)|(не определено)|  
  
 Вставьте сюда основную часть подраздела.  
  
###  <a name="OperationContract"></a>Атрибуты контракта операции  
  
|Имя свойства|Поддерживается|Описание|Проверка рабочего процесса|  
|-------------------|---------------|-----------------|-------------------|  
|Действие|Да|Возвращает или задает действие WS-Addressing сообщения запроса.|Свойство Receive.Action должно согласовываться.|  
|AsyncPattern|Нет|Указывает, что операция реализуется асинхронно с помощью блок Begin\<ИмяМетода > и End\<ИмяМетода > пары методов в контракте службы.|(не определено)|  
|HasProtectionLevel|Да|Возвращает значение, указывающее, должны ли сообщения этой операции шифроваться, подписываться или шифроваться и подписываться.|Свойство Receive.ProtectionLevel не должно иметь значение NULL.|  
|IsInitiating|Нет|Возвращает или задает значение, указывающее, реализует ли метод операцию, которая может инициировать сеанс на сервере (если такой сеанс существует).|(не определено)|  
|IsOneWay|Да|Возвращает или задает значение, указывающее, возвращает ли операция ответное сообщение.|(Не существует SendReply для этого Receive ИЛИ ReceiveReply для этого Send.)|  
|IsTerminating|Нет|Возвращает или задает значение, указывающее, приводит ли операция службы к закрытию сеанса сервером после отправки ответного сообщения, если оно есть.|(не определено)|  
|Имя|Да|Возвращает или задает имя операции.|Свойство Receive.OperationName должно согласовываться.|  
|ProtectionLevel|Да|Возвращает или задает значение, указывающее, должны ли сообщения операции шифроваться, подписываться или шифроваться и подписываться.|Свойство Receive.ProtectionLevel должно согласовываться.|  
|ReplyAction|Да|Возвращает или задает значение действия SOAP для ответного сообщения операции.|Свойство SendReply.Action должно согласовываться.|  
|TypeId|Нет|В случае реализации в производном классе возвращает уникальный идентификатор для этого атрибута. (Наследуется от атрибута.)|(не определено)|  
  
###  <a name="MessageContract"></a>Атрибуты контракта сообщения  
  
|Имя свойства|Поддерживается|Описание|Проверка рабочего процесса|  
|-------------------|---------------|-----------------|-------------------|  
|HasProtectionLevel|Да|Возвращает значение, указывающее, присвоен ли сообщению уровень защиты.|Проверка не выполняется (Receive.Content и SendReply.Content должны согласовываться с типом контракта сообщения).|  
|IsWrapped|Да|Возвращает или задает значение, указывающее, имеет ли текст сообщения элемент программы-оболочки.|Проверка не выполняется (Receive.Content и Sendreply.Content должны согласовываться с типом контракта сообщения).|  
|ProtectionLevel|Нет|Возвращает или задает значение, указывающее, необходимо ли шифровать сообщение, подписывать его или и то и другое.|(не определено)|  
|TypeId|Да|В случае реализации в производном классе возвращает уникальный идентификатор для этого атрибута. (Наследуется от атрибута.)|Проверка не выполняется (Receive.Content и SendReply.Content должны согласовываться с типом контракта сообщения).|  
|WrapperName|Да|Возвращает или задает имя элемента программы-оболочки текста сообщения.|Проверка не выполняется (Receive.Content и SendReply.Content должны согласовываться с типом контракта сообщения).|  
|WrapperNamespace|Нет|Возвращает или задает пространство имен элемента программы-оболочки текста сообщения.|(не определено)|  
  
###  <a name="DataContract"></a>Атрибуты контракта данных  
  
|Имя свойства|Поддерживается|Описание|Проверка рабочего процесса|  
|-------------------|---------------|-----------------|-------------------|  
|IsReference|Нет|Возвращает или задает значение, указывающее, следует ли сохранять данные ссылки на объект.|(не определено)|  
|Имя|Да|Возвращает или задает имя для контракта данных типа.|Проверка не выполняется (Receive.Content и SendReply.Content должны согласовываться с типом контракта сообщения).|  
|Пространство имен|Да|Возвращает или задает пространство имен для контракта данных типа.|Проверка не выполняется (Receive.Content и SendReply.Content должны согласовываться с типом контракта сообщения).|  
|TypeId|Нет|В случае реализации в производном классе возвращает уникальный идентификатор для этого атрибута. (Наследуется от атрибута.)|(не определено)|  
  
###  <a name="FaultContract"></a>Атрибуты контракта ошибок  
  
|Имя свойства|Поддерживается|Описание|Проверка рабочего процесса|  
|-------------------|---------------|-----------------|-------------------|  
|Действие|Да|Возвращает или задает действие сообщения об ошибке SOAP, которое задается как компонент контракта операции.|Свойство SendReply.Action должно согласовываться.|  
|DetailType|Да|Возвращает тип сериализуемого объекта, который содержит информацию об ошибке.|Свойство SendReply.Content должно согласовываться с типом.|  
|HasProtectionLevel|Нет|Возвращает значение, указывающее, присвоен ли сообщению об ошибке SOAP уровень защиты.|(не определено)|  
|Имя|Нет|Возвращает или задает имя сообщения об ошибке в языке WSDL.|(не определено)|  
|Пространство имен|Нет|Возвращает или задает пространство имен ошибки SOAP.|(не определено)|  
|ProtectionLevel|Нет|Задает уровень защиты, который требуется от привязки для ошибки SOAP.|(не определено)|  
|TypeId|Нет|В случае реализации в производном классе возвращает уникальный идентификатор для этого атрибута. (Наследуется от атрибута.)|(не определено)|  
  
##  <a name="AdditionalSupport"></a>Дополнительные сведения и сведения о реализации  
  
-   [Неподдерживаемые возможности контракта службы](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
-   [Создание настроенных действий обмена сообщениями](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ActivityGeneration)  
  
###  <a name="UnsupportedFeatures"></a>Неподдерживаемые возможности контракта службы  
  
-   Использовать библиотеку параллельных задач (TPL) в контрактах невозможно.  
  
-   Наследование в контрактах службы не поддерживается.  
  
###  <a name="ActivityGeneration"></a>Создание настроенных действий обмена сообщениями  
 Два общих статических метода добавляются в действия <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply> для поддержки создания предварительно настроенных действий сообщения, если используются службы рабочих процессов на основе контракта.  
  
-   <xref:System.ServiceModel.Activities.Receive.FromOperationDescription%2A?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Activities.SendReply.FromOperationDescription%2A?displayProperty=nameWithType>  
  
 Действие, созданное этими методами, должно пройти проверку по контракту и поэтому используется как часть логики проверки для <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>. Действия <xref:System.ServiceModel.Activities.Receive.OperationName%2A>, <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>, <xref:System.ServiceModel.Activities.Receive.Action%2A>, <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, <xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A> и <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> предварительно настроены для соответствия импортированному контракту. На странице свойств содержимого для действий в конструкторе рабочих процессов **сообщение** или **параметры** разделы предварительно настроены для соответствия контракту.  
  
 Настроить WCF проблем, контрактов также обрабатываются путем возвращения отдельный набор <xref:System.ServiceModel.Activities.SendReply> действия для каждой ошибки, которые отображаются в <xref:System.ServiceModel.Description.OperationDescription.Faults%2A> <xref:System.ServiceModel.Description.FaultDescriptionCollection>.  
  
 Для других частей <xref:System.ServiceModel.Description.OperationDescription> , не поддерживаются в службах WF сегодня (поведение WebGet/WebInvoke или поведение пользовательской операции), API обрабатывает их как часть создания и настройки. Исключения не формируются.
