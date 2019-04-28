---
title: Поле HttpWebRequest._CoreResponse
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
ms.openlocfilehash: 3627c9bf0d72ccec3a0d6d9c7c89b62f83dcd4b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706069"
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest. \_CoreResponse поля

`HttpWebRequest._CoreResponse` — Это объект (либо [CoreResponseData](coreresponsedata.md) или <xref:System.Exception>) содержащее результат синтаксического анализа ответа HTTP.

## <a name="syntax"></a>Синтаксис
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Этот API не предназначен для непосредственного использования в коде. Вместо этого следует использовать <xref:System.Diagnostics.DiagnosticSource> для подключения сетевого кода. См. в разделе [руководство пользователя DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Майкрософт не поддерживает использование этого класса в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Системы (в System.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.
