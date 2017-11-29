---
title: "s_isDebuggerCheckDisabledForTestPurposes поля"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
api_name: System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location: PresentationCore.dll
api_type: Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
robots: noindex,nofollow
ms.openlocfilehash: 97e5d32bff3e3150b56e8d9492aacc40f09f2afe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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

**Пространство имен:**<xref:System.Windows.Diagnostics>

**Сборка:** PresentationCore (в PresentationCore.dll)

**Версии платформы .NET framework:** доступно с версии 4.6.
