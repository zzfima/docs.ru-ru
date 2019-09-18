---
title: Включение отладки с JIT-присоединением (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4d4e2b3806d2c4d84b59e1cd44eb03ab7b278c9
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052825"
---
# <a name="enabling-jit-attach-debugging"></a>Включение отладки с JIT-присоединением (трассировка событий Windows)
Отладка с JIT-присоединением предусматривает присоединение отладчика к процессу при возникновении ошибок. Также этот процесс может запускаться посредством определенных методов или функций.  
  
 Отладка с JIT-присоединением используется при следующих условиях сбоя:  
  
- Необработанные исключения (в машинном и управляемом коде).  
  
- Метод <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> или функция [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) (семейство ОС Windows 7).  
  
- Неустранимые ошибки времени выполнения.  
  
 Отладка с JIT-присоединением также запускается посредством вызова следующих методов и функций:  
  
- Метод <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.  
  
- Метод <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.  
  
- Функция [DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) (Win32).  
  
 Перед .NET Framework 4 в .NET Framework предоставлены отдельные разделы реестра для управления поведением отладчиков машинного и управляемого кода. Начиная с .NET Framework 4, управление консолидируется в одном разделе реестра: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Значения этого раздела определяют, будет ли вызываться отладчик, а также будет ли в случае его вызова отображаться диалоговое окно для взаимодействия с пользователем. Сведения об установке этого раздела реестра см. в разделе [Настройка автоматической отладки](https://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>См. также

- [Отладка, трассировка и профилирование](index.md)
- [Упрощение отладки образов](making-an-image-easier-to-debug.md)
