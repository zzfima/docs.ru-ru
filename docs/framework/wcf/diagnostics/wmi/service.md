---
title: Служба
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374219"
---
# <a name="service"></a>Служба
Служба  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс Service не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс Service имеет следующие свойства.  
  
### <a name="baseaddresses"></a>BaseAddresses  
 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Базовые адреса, используемые службой.  
  
### <a name="behaviors"></a>поведения  
 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Поведения, связанные с этой службой.  
  
### <a name="configurationname"></a>ConfigurationName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 ServiceElement_BehaviorConfiguration  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя экземпляра счетчиков производительности службы.  
  
### <a name="distinguishedname"></a>DistinguishedName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя службы по адресу.  
  
### <a name="extensions"></a>Расширения  
 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Контексты экземпляра для расширений экземпляра службы.  
  
### <a name="metadata"></a>Метаданные  
 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Параметры метаданных службы.  
  
### <a name="name"></a>name  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Уникальное имя службы.  
  
### <a name="namespace"></a>Пространство имен  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Пространство имен службы.  
  
### <a name="opened"></a>Открыто  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Время открытия службы.  
  
### <a name="outgoingchannels"></a>OutgoingChannels  
 Тип данных: массив Channel  
  
 Тип доступа: только для чтения  
  
 Каналы, исходящие из экземпляра службы.  
  
### <a name="processid"></a>ProcessId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Возвращает ИД процесса, который размещает службу.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
