---
title: s_isDebuggerCheckDisabledForTestPurposes поля
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
robots: noindex,nofollow
ms.openlocfilehash: fbbd8d33ea163efaad1417ab4a1435df729e4897
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752212"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>s_isDebuggerCheckDisabledForTestPurposes поля

Это закрытое поле в `System.Windows.Diagnostics.VisualDiagnostics` класс используется средой Visual Studio, чтобы определить, будет ли выполняться внутренняя проверка для активного отладчика.

## <a name="syntax"></a>Синтаксис
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  API-Интерфейсы в `System.Windows.Diagnostics.VisualDiagnostics` класса доступны только в случае, когда приложение выполняется в режиме отладки. Задать `s_isDebuggerCheckDisabledForTestPurposes` для `true` для доступа к API вне отладчика.  
>   
>  Корпорация Майкрософт не поддерживает использование этого поля в реальном приложении ни при каких обстоятельствах.  

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Windows.Diagnostics>

**Сборка:** PresentationCore (в PresentationCore.dll)

**Версии платформы .NET framework:** доступно с версии 4.6.
