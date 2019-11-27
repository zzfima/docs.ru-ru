---
title: Настройка асинхронного приложения
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: 51786993cf16cd12b39cde3d47832191b3fdca8d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345836"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Точная настройка асинхронного приложения (Visual Basic)
Методы и свойства, доступные при использовании типа <xref:System.Threading.Tasks.Task>, позволяют сделать приложение более точным и гибким. В подразделах этого раздела приводятся примеры, в которых используются <xref:System.Threading.CancellationToken> и важные методы `Task`, такие как <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 С помощью `WhenAny` и `WhenAll` можно легко запускать несколько задач и ожидать их завершения путем наблюдения за одной из них.  
  
- `WhenAny` возвращает задачу, которая завершается после завершения любой задачи в коллекции.  
  
     Примеры использования `WhenAny`см. в разделе [Отмена оставшихся асинхронных задач после ее завершения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)и [Запуск нескольких асинхронных задач и их обработка по мере их завершения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
- `WhenAll` возвращает задачу, которая завершается после завершения всех задач в коллекции.  
  
     Дополнительные сведения и пример использования `WhenAll`см. в разделе [Практическое руководство. расширение асинхронного пошагового руководства с помощью Task. WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Этот раздел содержит следующие примеры.  
  
- [Отмена асинхронной задачи или списка задач (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).  
  
- [Отмена асинхронных задач после определенного периода времени (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
- [Отмена оставшихся асинхронных задач после завершения одной операции (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [Запуск нескольких асинхронных задач и их обработка по мере их завершения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.  
  
 Проекты создают пользовательский интерфейс, содержащий кнопку, которая запускает процесс, и кнопку, которая его отменяет, как показано на следующем рисунке. Кнопки называются `startButton` и `cancelButton`.  
  
 ![Окно WPF с кнопкой "Отмена"](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Диалоговое окно с кнопкой запуска и остановки")  
  
 Скачать полный проект Windows Presentation Foundation (WPF) можно со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).  
  
## <a name="see-also"></a>См. также

- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
