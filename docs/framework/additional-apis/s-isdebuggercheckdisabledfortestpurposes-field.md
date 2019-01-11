---
title: Поле s_isDebuggerCheckDisabledForTestPurposes
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ada3abcccac4244819cfbef1101a770761df6a50
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221925"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>Поле s_isDebuggerCheckDisabledForTestPurposes

Это частное поле в `System.Windows.Diagnostics.VisualDiagnostics` класс используется средой Visual Studio, чтобы определить, будет ли выполняться внутренняя проверка для активного отладчика.

## <a name="syntax"></a>Синтаксис
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  API в `System.Windows.Diagnostics.VisualDiagnostics` класса доступны только в случае, когда приложение выполняется в режиме отладки. Задайте `s_isDebuggerCheckDisabledForTestPurposes` для `true` для доступа к API вне отладчика.  
>   
>  Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.  

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Windows.Diagnostics>

**Сборка:** PresentationCore (в PresentationCore.dll)

**Версии платформы .NET framework:** Доступно с версии 4.6.