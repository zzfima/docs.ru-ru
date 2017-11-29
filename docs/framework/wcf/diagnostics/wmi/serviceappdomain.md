---
title: ServiceAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 36048f56c3b54447a112e6f0a457624062ce965a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
