---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 12e9cbf5232ebbad33ccc4fdca33233997d27357
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371567"
---
# <a name="contract"></a>Контракт
Контракт  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс контракта не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс контракта имеет следующие свойства.  
  
### <a name="appdomainid"></a>AppDomainId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор домена приложения, который размещает контракт.  
  
### <a name="behaviors"></a>Расширения функциональности  
 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Поведения, связанные с этим контрактом.  
  
### <a name="name"></a>name  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя контракта в WSDL.  
  
### <a name="namespace"></a>Пространство имен  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Пространство имен элемента `portType` в WSDL.  
  
### <a name="operations"></a>Операции  
 Тип данных: массив Operation  
  
 Тип доступа: только для чтения  
  
 Операции данного контракта.  
  
### <a name="processid"></a>ProcessId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор процесса, который размещает контракт.  
  
### <a name="ref"></a>ref  
 Тип данных: Contract  
  
 Тип доступа: только для чтения  
  
 Тип обратного вызова, когда контракт является дуплексным.  
  
### <a name="sessionmode"></a>SessionMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает, требуется ли для контракта, чтобы связанная с ним привязка использовала сеансы канала.  
  
### <a name="type"></a>Тип  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Тип контракта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.ContractDescription>
