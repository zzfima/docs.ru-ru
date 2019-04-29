---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957077"
---
# <a name="serviceappdomain"></a>ServiceAppDomain
Сопоставляет службу с доменом приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceAppDomain не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceAppDomain имеет следующие свойства.  
  
### <a name="ref"></a>ref  
 Тип данных: Служба  
Квалификаторы: Ключ  
  
 Тип доступа: Только чтение  
  
 Служба этого домена приложения.  
  
### <a name="ref"></a>ref  
 Тип данных: AppDomainInfo  
Квалификаторы: Ключ  
  
 Тип доступа: Только чтение  
  
 Содержит свойства домена приложения.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
