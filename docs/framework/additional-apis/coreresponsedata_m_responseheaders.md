---
title: Поле CoreResponseData.m_ResponseHeaders
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705978"
---
# <a name="coreresponsedatamresponseheaders-field"></a>CoreResponseData.m\_ResponseHeaders поля

`CoreResponseData.m_ResponseHeaders` является <xref:System.Net.WebHeaderCollection> заголовков, связанные с ответом сервера.

## <a name="syntax"></a>Синтаксис
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> Этот API не предназначен для непосредственного использования в коде. Вместо этого следует использовать <xref:System.Diagnostics.DiagnosticSource> для подключения сетевого кода. См. в разделе [руководство пользователя DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Майкрософт не поддерживает использование этого класса в рабочем приложении ни при каких обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Системы (в System.dll)

**Версии платформы .NET framework:** Доступно с версии 2.0.
