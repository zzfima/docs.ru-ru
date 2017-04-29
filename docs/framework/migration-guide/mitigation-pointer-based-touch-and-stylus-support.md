---
title: "Устранение рисков. Поддержка сенсорного управления и пера на основе указателя | Документация Майкрософт"
ms.custom: 
ms.date: 04/07/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
caps.latest.revision: 2
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9460c8b6ca8db927af4064e3567eca34c1bf5c91
ms.openlocfilehash: f93c914e0c1d285cc0f6117e5ae7a0f6338bc549
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a>Устранение рисков. Устранение рисков. Поддержка сенсорного управления и пера на основе указателя

В приложениях WPF, предназначенных 4.7 .NET Framework и выполняемых в системах Windows, начиная с версии Windows 10 Creators Update, можно включить дополнительный стек сенсорного управления и пера WPF на основе `WM_POINTER`.

## <a name="impact"></a>Последствия

Разработчики, которые явно не включают поддержку сенсорного управления или пера на основе указателя, не должны заметить изменений в поведении сенсорного управления или пера WPF.

Ниже перечислены текущие известные проблемы с дополнительным стеком сенсорного управления и пера на основе `WM_POINTER`.

- Не поддерживается рукописный ввод в режиме реального времени.

   Хотя подключаемые модули рукописного ввода и пера продолжают работать, они обрабатываются в потоке пользовательского интерфейса, что может вести к снижению производительности.

- Изменения поведения из-за изменений в переходе от событий сенсорного управления или пера к событиям мыши.

  - Обработка может выполняться по-разному.

  - При перетаскивании не будет показана соответствующая реакция на сенсорный ввод. (Это не влияет на ввод с помощью пера).

  - Перетаскивание больше нельзя инициировать при событиях сенсорного управления или пера.

      Это потенциально может вызвать зависание приложения до обнаружения ввода с помощью мыши. Вместо этого разработчикам следует инициировать перетаскивание с помощью событий мыши.

## <a name="opting-in-to-wmpointer-based-touchstylus-support"></a>Выбор поддержки сенсорного управления и пера на основе WM_POINTER

Разработчики, желающие включить этот стек, могут добавить следующую информацию в файл app.config своего приложения:

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

Удаление этой записи или присвоение ей значения `false` отключает данный дополнительный стек.

## <a name="see-also"></a>См. также

[Изменения целевой платформы в .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

