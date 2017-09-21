---
title: "Включение отладки с JIT-присоединением (трассировка событий Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: 17
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5ca6d1e6ec5c19f690ab862b13783b9db05ac2a9
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="enabling-jit-attach-debugging"></a>Включение отладки с JIT-присоединением (трассировка событий Windows)
Отладка с JIT-присоединением предусматривает присоединение отладчика к процессу при возникновении ошибок. Также этот процесс может запускаться посредством определенных методов или функций.  
  
 Отладка с JIT-присоединением используется при следующих условиях сбоя:  
  
-   Необработанные исключения (в машинном и управляемом коде).  
  
-   Метод <xref:System.Environment.FailFast%2A?displayProperty=fullName> или функция [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) (семейство ОС Windows 7).  
  
-   Неустранимые ошибки времени выполнения.  
  
 Отладка с JIT-присоединением также запускается посредством вызова следующих методов и функций:  
  
-   Метод <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=fullName>.  
  
-   Метод <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=fullName>.  
  
-   Функция [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) (Win32).  
  
 В версиях платформы .NET Framework до [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] были представлены отдельные разделы реестра, определяющие поведение отладчиков машинного и управляемого кода. Начиная с версии [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], эти функции управления объединены в одном разделе реестра: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Значения этого раздела определяют, будет ли вызываться отладчик, а также будет ли в случае его вызова отображаться диалоговое окно для взаимодействия с пользователем. Дополнительные сведения о настройке этого раздела реестра см. на странице [Настройка автоматической отладки](http://go.microsoft.com/fwlink/?LinkId=181767) в библиотеке MSDN.  
  
## <a name="see-also"></a>См. также  
 [Отладка, трассировка и профилирование](../../../docs/framework/debug-trace-profile/index.md)   
 [Упрощение отладки образов](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)   
 [Включение профилирования](http://msdn.microsoft.com/en-us/3b669676-f0e0-4ebf-8674-68986dd2020d)

