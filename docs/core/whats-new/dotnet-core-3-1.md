---
title: Новые возможности .NET Core 3.1
description: Дополнительные сведения о новых возможностях .NET Core 3.1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 0905cbebb2d966570be4ac3aefb40f4377b97061
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742588"
---
# <a name="whats-new-in-net-core-31"></a>Новые возможности .NET Core 3.1

В этой статье описаны новые возможности в .NET Core 3.1. Этот выпуск содержит небольшие улучшения относительно .NET Core 3.0. Внимание уделялось нескольким небольшим, но важным исправлениям. Основная особенность .NET Core 3.1 заключается в том, что это выпуск [долгосрочной поддержки (LTS)](#long-term-support).

Если вы используете Visual Studio 2019, для работы с проектами .NET Core 3.1 необходимо обновить Visual Studio 2019 до [версии 16.4](https://visualstudio.microsoft.com/downloads/). Дополнительные сведения о новых возможностях Visual Studio см. на странице [Новые возможности Visual Studio 2019 версии 16.4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).

Visual Studio для Mac также поддерживает и содержит .NET Core 3.1 в версии Visual Studio для Mac 8.4.

Дополнительные сведения см. в [объявлении о выпуске .NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).

- [Скачайте .NET Core 3.1 и начните работу](https://dotnet.microsoft.com/download/dotnet-core/3.1) в Windows, macOS или Linux.

## <a name="long-term-support"></a>Долгосрочная поддержка

.NET Core 3.1 объявляется выпуском долгосрочной поддержки. Это означает, что корпорация Майкрософт будет поддерживать его в течение следующих трех лет. Мы настоятельно рекомендуем перевести все приложения на .NET Core 3.1. Текущий жизненный цикл других основных выпусков:

| Выпуск | Примечание. |
| ------- | ---- |
| .NET Core 3.0 | Окончание жизненного цикла 3 марта 2020 г.     |
| .NET Core 2.2 | Окончание жизненного цикла 23 декабря 2019 г. |
| .NET Core 2.1 | Окончание жизненного цикла 21 августа 2021 г.    |

Дополнительные сведения см. в статье о [политике поддержки .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="windows-forms"></a>Windows Forms

*Только для Windows*

> [!WARNING]
> В Windows Forms внесены критические изменения.

В Windows Forms входили устаревшие элементы управления, которые уже некоторое время недоступны на панели элементов конструктора Visual Studio. Они были заменены новыми элементами управления еще в .NET Framework 2.0. Эти элементы управления удалены из пакета SDK для рабочего стола для .NET Core 3.1.

| Удаленный элемент управления | Рекомендуемая замена | Соответствующие удаленные интерфейсы API |
| --------------- | ----------------------- | ----------------------- |
| DataGrid        | <xref:System.Windows.Forms.DataGridView>      | DataGridCell<br/>DataGridRow<br/>DataGridTableCollection<br/>DataGridColumnCollection<br/>DataGridTableStyle<br/>DataGridColumnStyle<br/>DataGridLineStyle<br/>DataGridParentRowsLabel<br/>DataGridParentRowsLabelStyle<br/>DataGridBoolColumn<br/>DataGridTextBox<br/>GridColumnStylesCollection<br/>GridTableStylesCollection<br/>HitTestType |
| ToolBar         | <xref:System.Windows.Forms.ToolStrip>         | ToolBarAppearance |
| ToolBarButton   | <xref:System.Windows.Forms.ToolStripButton>   | ToolBarButtonClickEventArgs<br/>ToolBarButtonClickEventHandler<br/>ToolBarButtonStyle<br/>ToolBarTextAlign |
| ContextMenu     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | MenuItemCollection |
| MainMenu        | <xref:System.Windows.Forms.MenuStrip>         |  |
| MenuItem        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

Мы рекомендуем обновить все приложения до .NET Core 3.1 и перейти к использованию рекомендованных заменяющих элементов управления. Замена элементов управления не представляет никаких сложностей. Достаточно найти и заменить все вхождения имени типа.

## <a name="ccli"></a>C++/CLI

*Только для Windows*

Добавлена поддержка создания проектов C++/CLI ("управляемый C++"). Двоичные файлы из этих проектов совместимы с .NET Core 3.0 и более поздних версий.

Чтобы добавить поддержку C++/CLI в Visual Studio 2019 версии 16.4, установите рабочую нагрузку [Разработка классических приложений на C++](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads). При использовании этой рабочей нагрузки в Visual Studio добавляется два шаблона:

- библиотека классов CLR (.NET Core);
- пустой проект CLR (.NET Framework).

## <a name="next-steps"></a>Следующие шаги

- [Изучите критические изменения при обновлении с .NET Core 3.0 и до NET Core 3.1.](../compatibility/3.0-3.1.md)
- [Изучите критические изменения в NET Core 3.1 для приложений Windows Forms.](../compatibility/winforms.md#net-core-31)
