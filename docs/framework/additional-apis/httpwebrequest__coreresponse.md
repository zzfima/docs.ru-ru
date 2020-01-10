---
title: HttpWebRequest. _CoreResponse поле
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740447"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest.\_поле Коререспонсе

`HttpWebRequest._CoreResponse` — это объект ( [коререспонседата](coreresponsedata.md) или <xref:System.Exception>), содержащий результат синтаксического анализа ответа HTTP.

## <a name="syntax"></a>Синтаксис
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Этот API не предназначен для непосредственного использования в коде. Вместо этого следует использовать <xref:System.Diagnostics.DiagnosticSource> для подключения сетевого кода. Ознакомьтесь с [руководством пользователя DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System. dll)

**.NET Framework версии:** Доступно с 2,0.
