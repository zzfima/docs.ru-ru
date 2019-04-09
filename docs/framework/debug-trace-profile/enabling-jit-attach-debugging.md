---
title: Включение отладки с JIT-присоединением (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1696f9054d44a5f80a1f67cc38e315a8627d295
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078788"
---
# <a name="enabling-jit-attach-debugging"></a>Включение отладки с JIT-присоединением (трассировка событий Windows)
Отладка с JIT-присоединением предусматривает присоединение отладчика к процессу при возникновении ошибок. Также этот процесс может запускаться посредством определенных методов или функций.  
  
 Отладка с JIT-присоединением используется при следующих условиях сбоя:  
  
-   Необработанные исключения (в машинном и управляемом коде).  
  
-   <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> метод или [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) функция (семейство Windows 7).  
  
-   Неустранимые ошибки времени выполнения.  
  
 Отладка с JIT-присоединением также запускается посредством вызова следующих методов и функций:  
  
-   <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> метод.  
  
-   <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> метод.  
  
-   Функция [DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) (Win32).  
  
 В версиях платформы .NET Framework до [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] были представлены отдельные разделы реестра, определяющие поведение отладчиков машинного и управляемого кода. Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], элемент управления, объединяются в одном разделе реестра: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Значения этого раздела определяют, будет ли вызываться отладчик, а также будет ли в случае его вызова отображаться диалоговое окно для взаимодействия с пользователем. Сведения о настройке раздела реестра, см. в разделе [Настройка автоматической отладки](https://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>См. также

- [Отладка, трассировка и профилирование](../../../docs/framework/debug-trace-profile/index.md)
- [Упрощение отладки образов](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
