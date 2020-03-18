---
title: Основные и фоновые потоки
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 9e93f07b3b84264373db0317919b6ee519c8127c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138055"
---
# <a name="foreground-and-background-threads"></a>Основные и фоновые потоки
Управляемый поток может быть основным или фоновым. Фоновые потоки отличаются от основных только в одном аспекте: фоновый поток не поддерживает работу управляемой среды выполнения. После того, как в управляемом процессе (где управляемой сборкой является файл EXE) остановятся все основные потоки, система принудительно останавливает все фоновые потоки и завершает работу процесса.  
  
> [!NOTE]
> Когда в среде выполнения останавливается фоновый поток из-за завершения работы процесса, исключение в потоке не возникает. Но если потоки останавливаются из-за выгрузки домена приложения в методе <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>, во всех основных и фоновых потоках создается исключение <xref:System.Threading.ThreadAbortException>.  
  
 Свойство <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> позволяет определить, является ли поток основным или фоновым, а также изменить его статус. Поток можно в любой момент сделать фоновым, задав в нем для свойства <xref:System.Threading.Thread.IsBackground%2A> значение `true`.  
  
> [!IMPORTANT]
> Основное или фоновое состояние потока не влияет на поведение необработанного исключения в потоке. На платформе .NET Framework версии 2.0 необработанное исключение в основном или фоновом потоке приведет к завершению работы приложения. См. также [Исключения в управляемых потоках](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Потоки, входящие в пул управляемых потоков (то есть потоки, в которых для свойства <xref:System.Threading.Thread.IsThreadPoolThread%2A> задано значение `true`), считаются фоновыми потоками. Все потоки, которые включаются в управляемую среду выполнения из неуправляемого кода, помечаются как фоновые потоки. Все потоки, созданные путем создания и запуска нового объекта <xref:System.Threading.Thread>, по умолчанию становятся основными потоками.  
  
 Если у вас есть поток, который отслеживает некоторое действие, например подключение через сокет, установите для его свойства <xref:System.Threading.Thread.IsBackground%2A> значение `true`, чтобы этот поток не мешал завершить процесс.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>
