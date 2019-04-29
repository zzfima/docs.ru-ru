---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 10789f9a2940c239ae20c8fd1e9d48bca0e820ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963700"
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
  
 Тип доступа: Только чтение  
  
 Идентификатор домена приложения, который размещает контракт.  
  
### <a name="behaviors"></a>поведения  
 Тип данных: Массив Behavior  
  
 Тип доступа: Только чтение  
  
 Поведения, связанные с этим контрактом.  
  
### <a name="name"></a>name  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Имя контракта в WSDL.  
  
### <a name="namespace"></a>Пространство имен  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Пространство имен элемента `portType` в WSDL.  
  
### <a name="operations"></a>Операции  
 Тип данных: Массив Operation  
  
 Тип доступа: Только чтение  
  
 Операции данного контракта.  
  
### <a name="processid"></a>ProcessId  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Идентификатор процесса, который размещает контракт.  
  
### <a name="ref"></a>ref  
 Тип данных: Контракт  
  
 Тип доступа: Только чтение  
  
 Тип обратного вызова, когда контракт является дуплексным.  
  
### <a name="sessionmode"></a>SessionMode  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Указывает, требуется ли для контракта, чтобы связанная с ним привязка использовала сеансы канала.  
  
### <a name="type"></a>Тип  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Тип контракта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ContractDescription>
