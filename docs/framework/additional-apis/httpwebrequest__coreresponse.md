---
title: HttpWebRequest._CoreResponse поле
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
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155925"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest. \_Поле CoreResponse

`HttpWebRequest._CoreResponse`— объект (либо [CoreResponseData,](coreresponsedata.md) либо <xref:System.Exception>), содержащий результат анализа ответов HTTP.

## <a name="syntax"></a>Синтаксис
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Этот API не предназначен для использования непосредственно в коде. Вместо этого следует <xref:System.Diagnostics.DiagnosticSource> использовать сетевой код. Смотрите [руководство DiagnosticSource пользователя](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
>
> Корпорация Майкрософт ни при каких обстоятельствах не поддерживает использование этого класса в производственном приложении.

## <a name="requirements"></a>Требования

**Пространство имен:**<xref:System.Net>

**Сборка:** Система (в System.dll)

**Рамочные версии .NET:** Доступно с 2.0.
