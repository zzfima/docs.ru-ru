---
title: Конечная точка
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 4562481e8b0b18c0ea0d9df0af3427ffe6419821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963609"
---
# <a name="endpoint"></a>Конечная точка
Конечная точка  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс Endpoint определяет следующий метод.  
  
|Метод|Описание|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|Извлекает имя экземпляра счетчика производительности операций|  
  
## <a name="properties"></a>Свойства  
 Класс Endpoint имеет следующие свойства.  
  
### <a name="address"></a>Адрес  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Универсальный код ресурса (URI), содержащий адрес конечной точки.  
  
### <a name="addressheaders"></a>AddressHeaders  
 Тип данных: массив строк  
  
 Тип доступа: Только чтение  
  
 Коллекция заголовков адреса, прикрепленных к этой конечной точке.  
  
### <a name="addressidentity"></a>AddressIdentity  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Удостоверение конечной точки.  
  
### <a name="appdomainid"></a>AppDomainId  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Идентификатор домена приложения, который размещает конечную точку.  
  
### <a name="behaviors"></a>поведения  
 Тип данных: Массив Behavior  
  
 Тип доступа: Только чтение  
  
 Коллекция поведений, реализуемых этой конечной точкой.  
  
### <a name="binding"></a>Привязка  
 Тип данных: Привязка  
  
 Тип доступа: Только чтение  
  
 Привязка, используемая этой конечной точкой.  
  
### <a name="contractname"></a>ContractName  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Строка, в которой указывается, какой контракт предоставляется этой конечной точкой.  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Имя экземпляра счетчиков производительности конечной точки.  
  
### <a name="listenuri"></a>ListenUri  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Универсальный код ресурса (URI), от которого данная конечная точка ожидает передачи данных.  
  
### <a name="name"></a>name  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Уникальное имя конечной точки.  
  
### <a name="processid"></a>ProcessId  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Возвращает идентификатор процесса, который размещает конечную точку.  
  
### <a name="ref"></a>ref  
 Тип данных: Контракт  
  
 Тип доступа: Только чтение  
  
 Контракт, предоставляемый этой конечной точкой.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
