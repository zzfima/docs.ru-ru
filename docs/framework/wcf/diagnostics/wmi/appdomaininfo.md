---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127086"
---
# <a name="appdomaininfo"></a>AppDomainInfo
Сведения о домене приложения  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс AppDomainInfo не определяет никакие методы.  
  
## <a name="properties"></a>Свойства  
 Класс AppDomainInfo имеет следующие свойства.  
  
### <a name="appdomainid"></a>AppDomainId  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Идентификатор домена приложения.  
  
### <a name="isdefault"></a>IsDefault  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, является ли домен приложения доменом приложения, используемым по умолчанию.  
  
### <a name="logmalformedmessages"></a>LogMalformedMessages  
 Тип данных: boolean  
  
 Тип доступа: Чтение и запись  
  
 Значение, указывающее, заносятся ли в журнал неправильные сообщения.  
  
### <a name="logmessagesatservicelevel"></a>LogMessagesAtServiceLevel  
 Тип данных: boolean  
  
 Тип доступа: Чтение и запись  
  
 Значение, указывающее, трассируются ли сообщения на уровне службы (перед шифрованием и преобразованиями, связанными с транспортом).  
  
### <a name="logmessagesattransportlevel"></a>LogMessagesAtTransportLevel  
 Тип данных: boolean  
  
 Тип доступа: Чтение и запись  
  
 Значение, указывающее, трассируются ли сообщения на уровне транспорта.  
  
### <a name="messageloggingtracelisteners"></a>MessageLoggingTraceListeners  
 Тип данных: Массив TraceListener  
  
 Тип доступа: Только чтение  
  
 Коллекция прослушивателей трассировки, которые ожидают передачи данных источнику трассировки System.Wmi.MessageLogging.  
  
### <a name="name"></a>name  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Имя домена приложения.  
  
### <a name="performancecounters"></a>PerformanceCounters  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Область активных счетчиков производительности в домене приложения.  
  
### <a name="processid"></a>ProcessId  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Идентификатор процесса.  
  
### <a name="serviceconfigpath"></a>ServiceConfigPath  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Путь к конфигурации службы.  
  
### <a name="tracelevel"></a>TraceLevel  
 Тип данных: string  
  
 Тип доступа: Чтение и запись  
  
 Уровень трассировки источника трассировки System.Wmi.  
  
### <a name="servicemodeltracelisteners"></a>ServiceModelTraceListeners  
 Тип данных: Массив TraceListener  
  
 Тип доступа: Только чтение  
  
 Коллекция прослушивателей, ожидающих передачи данных от источника трассировки System.ServiceModel.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
