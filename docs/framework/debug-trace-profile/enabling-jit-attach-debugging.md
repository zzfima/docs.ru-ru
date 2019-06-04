---
title: Включение отладки с JIT-присоединением (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 005395beabd956767b59e0cebd563fe883f6fe53
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489803"
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
  
 Прежде чем .NET Framework 4 .NET Framework представлены отдельные разделы реестра для управления поведением отладчиков машинного и управляемого кода. Начиная с .NET Framework 4, элемент управления является объединены в отдельного раздела реестра: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Значения этого раздела определяют, будет ли вызываться отладчик, а также будет ли в случае его вызова отображаться диалоговое окно для взаимодействия с пользователем. Сведения о настройке раздела реестра, см. в разделе [Настройка автоматической отладки](https://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>См. также

- [Отладка, трассировка и профилирование](../../../docs/framework/debug-trace-profile/index.md)
- [Упрощение отладки образов](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
