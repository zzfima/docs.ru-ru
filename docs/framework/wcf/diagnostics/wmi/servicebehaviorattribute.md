---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: 420686ebda7f23a5d883deece251b034147fafa4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654585"
---
# <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute
ServiceBehaviorAttribute  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceBehaviorAttribute не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceBehaviorAttribute имеет следующие свойства.  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, следует ли автоматически закрывать сеанс, когда клиент закрывает выходной сеанс.  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 Тип данных: string  
Тип доступа: Только чтение  
  
 Указывает, поддерживает служба один поток, несколько потоков или повторные входящие вызовы.  
  
### <a name="configurationname"></a>ConfigurationName  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Имя конфигурации службы.  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, требуется ли передать неизвестные данные сериализации по сети.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.  
  
### <a name="instancecontextmode"></a>InstanceContextMode  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Указывает, когда создается новый объект службы.  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальное количество элементов, допустимое в сериализованном объекте.  
  
### <a name="name"></a>name  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Имя атрибута службы в WSDL.  
  
### <a name="namespace"></a>Пространство имен  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Целевое пространство имен службы в WSDL.  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a>ReleaseServiceInstanceOnTransactionComplete  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, производится ли повторное использование объекта службы после завершения текущей транзакции.  
  
### <a name="transactionautocompleteonsessionclose"></a>TransactionAutoCompleteOnSessionClose  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, завершаются ли ожидающие транзакции при закрытии текущего сеанса.  
  
### <a name="transactionisolationlevel"></a>TransactionIsolationLevel  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Указывает уровень изоляции транзакции.  
  
### <a name="transactiontimeout"></a>TransactionTimeout  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Период времени, в течение которого транзакция должна быть завершена.  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, использовать ли текущий контекст синхронизации для выбора потока выполнения.  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, кем выполняется принудительная обработка заголовка SOAP MustUnderstand: системой или приложением.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.ServiceBehaviorAttribute>
