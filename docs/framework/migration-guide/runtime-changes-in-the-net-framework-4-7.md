---
title: "Изменения среды выполнения в .NET Framework 4.7 | Документация Майкрософт"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes,.NET Framework
- runtime changes,.NET Framework 4.7
- application compatibility
ms.assetid: 268eb334-7906-4e0b-a1e3-c74b745de2a5
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 321ec8f8293afad0f3da7fb6f907f45d404394cc
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-47"></a>Изменения среды выполнения в .NET Framework 4.7

В редких случаях изменения среды выполнения могут повлиять на существующие приложения, предназначенные для предыдущих версий .NET Framework, но выполняющиеся в более поздней версии среды выполнения .NET Framework. Они также включают различия в поведении между приложениями, которые выполняются в разных средах .NET Framework. Платформа .NET Framework 4.6.2 включает изменения в следующих областях:

- [Windows Presentation Foundation (WPF)](#WPF)

Столбец "Scope" в следующих таблицах определяет важность каждого изменения.

- Основное. Значительное изменение, влияющее на большое количество приложений или требующее существенного изменения кода. Обратите внимание, что ни одно из изменений целевой платформы не попадает в эту категорию.

- Незначительное. Изменение влияет на небольшое количество приложений или требует незначительного изменения кода.

- Пограничное. Изменение влияет на приложения в исключительных ситуациях.

- Прозрачное. Изменение не оказывает особого влияния на разработчика или пользователя приложения. При этом вносить изменения в приложения не требуется.

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" /> Windows Presentation Foundation (WPF)

assetId:///M:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView(System.Int32)?qualifyHint=False&autoUpgrade=True

| Функция | Изменение | Последствия | Область |
|---|---|---|---|
| Метод <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A> | В платформе .NET Framework 4.6.2 метод <xref:System.Windows.Controls.DataGridCellsPanel.BringIndexIntoView%2A> выполняется асинхронно, если виртуализация столбцов включена, но ширина столбцов не определена. Если столбцы удаляются до завершения асинхронной операции, может возникнуть исключение <xref:System.ArgumentOutOfRangeException>.<br/></br>Начиная с .NET Framework 4.7, исключение в этом сценарии больше не вызывается. | Это изменение повышает надежность метода. | Пограничный случай | 
|Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup> | В .NET Framework 4.6.2 и более ранних версиях фон элемента <xref:System.Windows.Controls.Ribbon.RibbonGroup> в локализованных сборках отрисовывался прозрачной кистью, что вело к снижению качества пользовательского интерфейса. В .NET Framework 4.7 WPF обновляет локализованные ресурсы для элемента управления <xref:System.Windows.Controls.Ribbon.RibbonGroup>, что гарантирует выбор правильной кисти. | Чтобы воспользоваться преимуществами нового поведения, обновите платформу .NET Framework до версии 4.7. | Пограничный случай |
| Средство проверки орфографии WPF | Начиная с .NET Framework 4.6.1 средство проверки орфографии в приложениях WPF иногда вызывает исключение <xref:System.ObjectDisposedException> при завершении работы приложения. <br/><br/>В .NET Framework 4.7 это исключение аккуратно обрабатывается средой выполнения, что обеспечивает отсутствие отрицательного влияния на работу приложений. Следует отметить, что случайные первичные исключения продолжают наблюдаться в приложениях, выполняемых в режиме отладки.  | Чтобы воспользоваться преимуществами нового поведения, обновите платформу .NET Framework до версии 4.7.   | Пограничный случай |

## <a name="see-also"></a>См. также

[Совместимость приложений в .NET Framework 4.7](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-7.md)


