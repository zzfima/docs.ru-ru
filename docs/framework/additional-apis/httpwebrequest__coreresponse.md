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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest. \_CoreResponse поля

`HttpWebRequest._CoreResponse` — Это объект (либо [CoreResponseData](coreresponsedata.md) или <xref:System.Exception>) содержащий результат синтаксическом разборе ответа HTTP.

## <a name="syntax"></a>Синтаксис
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Этот API не предназначен для непосредственного использования в коде. Вместо этого следует использовать <xref:System.Diagnostics.DiagnosticSource> отключают сетевого кода. В разделе [DiagnosticSource в руководстве пользователя](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> В реальном приложении ни при каких обстоятельствах корпорация Майкрософт не поддерживает использование этого класса.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** системы (в System.dll)

**Версии платформы .NET framework:** доступно с версии 2.0.
