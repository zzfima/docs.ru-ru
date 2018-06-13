---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485672"
---
# <a name="serviceappdomain"></a>ServiceAppDomain
Сопоставляет службу с доменом приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 Тип данных: Service  
Квалификаторы: ключ  
  
 Тип доступа: только для чтения  
  
 Служба этого домена приложения.  
  
### <a name="ref"></a>ref  
 Тип данных: AppDomainInfo  
Квалификаторы: ключ  
  
 Тип доступа: только для чтения  
  
 Содержит свойства домена приложения.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
