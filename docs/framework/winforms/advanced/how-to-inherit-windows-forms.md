---
title: Практическое руководство. Наследование форм Windows Forms
ms.date: 03/30/2017
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: a6d000bc853046cffbc2bddc54d1f5faec689032
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968618"
---
# <a name="how-to-inherit-windows-forms"></a>Практическое руководство. Наследование форм Windows Forms

Создание новых форм Windows Forms путем наследования базовых форм является удобным способом для дублирования уже созданного, минуя процесс повторного создания формы с нуля каждый раз, когда она необходима.

Дополнительные сведения о наследовании форм во время разработки с помощью диалогового окна **«Выбор наследования** » и о том, как визуально различать уровни безопасности [наследуемых элементов управления, см. в разделе как Наследовать формы с помощью диалогового окна](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)Выбор наследования.

> [!NOTE]
> Для наследования из формы файл или пространство имен, содержащие эту форму, должны быть встроены в исполняемый файл или библиотеку DLL. Для сборки проекта выберите в меню **Сборка** пункт **Собрать**. Кроме того необходимо добавить ссылку на пространство имен к классу, наследующему форму.

## <a name="inherit-a-form-programmatically"></a>Наследовать форму программным способом

1. В классе добавьте ссылку на пространство имен, содержащее форму, которую вы хотите наследовать.

2. В определении класса добавьте ссылку на форму для наследования. Ссылка должна содержать пространство имен, в котором содержится форма, точку, а затем имя базовой формы.

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 При наследовании форм следует помнить, что могут возникнуть проблемы с обработчиками событий, которые вызываются дважды, так как каждое событие обрабатывается базовым классом и производным классом. Дополнительные сведения о том, как избежать этой проблемы, см. в разделе [Устранение неполадок, связанных с унаследованными обработчиками событий в Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).

## <a name="see-also"></a>См. также

- [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [using](../../../csharp/language-reference/keywords/using.md)
- [Влияние изменения внешнего вида базовой формы](effects-of-modifying-base-form-appearance.md)
- [Визуальное наследование в Windows Forms](windows-forms-visual-inheritance.md)
