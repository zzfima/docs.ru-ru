---
title: Включение отладки с JIT-присоединением (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67db256f4c328b12d6cc30abfbe5d5ccc12e8b0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397836"
---
# <a name="enabling-jit-attach-debugging"></a>Включение отладки с JIT-присоединением (трассировка событий Windows)
Отладка с JIT-присоединением предусматривает присоединение отладчика к процессу при возникновении ошибок. Также этот процесс может запускаться посредством определенных методов или функций.  
  
 Отладка с JIT-присоединением используется при следующих условиях сбоя:  
  
-   Необработанные исключения (в машинном и управляемом коде).  
  
-   Метод <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> или функция [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) (семейство ОС Windows 7).  
  
-   Неустранимые ошибки времени выполнения.  
  
 Отладка с JIT-присоединением также запускается посредством вызова следующих методов и функций:  
  
-   Метод <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.  
  
-   Метод <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.  
  
-   Функция [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) (Win32).  
  
 В версиях платформы .NET Framework до [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] были представлены отдельные разделы реестра, определяющие поведение отладчиков машинного и управляемого кода. Начиная с версии [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], эти функции управления объединены в одном разделе реестра: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Значения этого раздела определяют, будет ли вызываться отладчик, а также будет ли в случае его вызова отображаться диалоговое окно для взаимодействия с пользователем. Сведения о настройке раздела реестра см. в разделе [Настройка автоматического отладки](http://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>См. также  
 [Отладка, трассировка и профилирование](../../../docs/framework/debug-trace-profile/index.md)  
 [Упрощение отладки образов](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 [Включение профилирования](http://msdn.microsoft.com/library/3b669676-f0e0-4ebf-8674-68986dd2020d)
