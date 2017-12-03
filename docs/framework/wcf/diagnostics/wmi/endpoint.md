---
title: "Конечная точка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed3c01f6943ec2958da56777ac0d6223fff66ab0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint"></a>Конечная точка
Конечная точка  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса (URI), содержащий адрес конечной точки.  
  
### <a name="addressheaders"></a>AddressHeaders  
 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Коллекция заголовков адреса, прикрепленных к этой конечной точке.  
  
### <a name="addressidentity"></a>AddressIdentity  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Удостоверение конечной точки.  
  
### <a name="appdomainid"></a>AppDomainId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор домена приложения, который размещает конечную точку.  
  
### <a name="behaviors"></a>Поведения  
 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Коллекция поведений, реализуемых этой конечной точкой.  
  
### <a name="binding"></a>Привязка  
 Тип данных: Binding  
  
 Тип доступа: только для чтения  
  
 Привязка, используемая этой конечной точкой.  
  
### <a name="contractname"></a>ContractName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Строка, в которой указывается, какой контракт предоставляется этой конечной точкой.  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя экземпляра счетчиков производительности конечной точки.  
  
### <a name="listenuri"></a>ListenUri  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса (URI), от которого данная конечная точка ожидает передачи данных.  
  
### <a name="name"></a>Имя  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Уникальное имя конечной точки.  
  
### <a name="processid"></a>ProcessId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Возвращает идентификатор процесса, который размещает конечную точку.  
  
### <a name="ref"></a>ref  
 Тип данных: Contract  
  
 Тип доступа: только для чтения  
  
 Контракт, предоставляемый этой конечной точкой.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
