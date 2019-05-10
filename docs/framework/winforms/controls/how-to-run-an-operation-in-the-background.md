---
title: Практическое руководство. Фоновое выполнение операции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: a27c6d83a6a132ed5a83031d469e2f527b730d49
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638385"
---
# <a name="how-to-run-an-operation-in-the-background"></a>Практическое руководство. Фоновое выполнение операции
Если какая-либо операция будет выполняться в течение долгого времени и при этом требуется не допустить задержек в работе пользовательского интерфейса, можно использовать класс <xref:System.ComponentModel.BackgroundWorker> для выполнения операции в другом потоке.  
  
 В примере ниже показано, как запустить операцию, занимающую длительное время, в фоновом режиме. В форме есть кнопки **Пуск** и **Отмена**. Кнопка **Пуск** служит для запуска асинхронной операции. Кнопка **Отмена** служит для остановки асинхронной операции. Результат каждой операции выводится в элементе <xref:System.Windows.Forms.MessageBox>.  
  
 В Visual Studio предусмотрена расширенная поддержка данной задачи.  
  
 Также см. в разделе [Пошаговое руководство: Выполнение операции в фоновом режиме](walkthrough-running-an-operation-in-the-background.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.  
  
## <a name="see-also"></a>См. также

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Компонент BackgroundWorker](backgroundworker-component.md)
