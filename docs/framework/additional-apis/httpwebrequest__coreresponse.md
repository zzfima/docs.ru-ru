---
title: "Поле HttpWebRequest._CoreResponse"
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6493747cf6c894357223f011da026770778e26c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest. \_CoreResponse поля

`HttpWebRequest._CoreResponse`— Это объект (либо [CoreResponseData](coreresponsedata.md) или <xref:System.Exception>) содержащий результат синтаксическом разборе ответа HTTP.

## <a name="syntax"></a>Синтаксис
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Этот API не предназначен для непосредственного использования в коде. Вместо этого следует использовать <xref:System.Diagnostics.DiagnosticSource> отключают сетевого кода. В разделе [DiagnosticSource в руководстве пользователя](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> В реальном приложении ни при каких обстоятельствах корпорация Майкрософт не поддерживает использование этого класса.

## <a name="requirements"></a>Требования

**Пространство имен:**<xref:System.Net>

**Сборка:** системы (в System.dll)

**Версии платформы .NET framework:** доступно с версии 2.0.
