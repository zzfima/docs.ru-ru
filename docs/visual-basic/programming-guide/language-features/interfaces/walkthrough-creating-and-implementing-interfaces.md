---
title: Создание и реализация интерфейсов
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 47176d2e7a512d8e8c27a90ac04d2a2a2af274b5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345042"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Пошаговое руководство. Создание и реализация интерфейсов (Visual Basic)

Интерфейсы описывают характеристики свойств, методов и событий, но не содержат сведений о реализации до структур или классов.  
  
 В этом пошаговом руководстве показано, как объявить и реализовать интерфейс.  
  
> [!NOTE]
> В этом пошаговом руководстве не содержатся сведения о создании пользовательского интерфейса.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Определение интерфейса
  
1. Откройте новый проект приложения Windows на Visual Basic.  
  
2. Добавьте в проект новый модуль, выбрав в меню **проект** пункт **Добавить модуль** .  
  
3. Присвойте новому модулю имя `Module1.vb` и нажмите кнопку **Добавить**. Отобразится код для нового модуля.  
  
4. Определите интерфейс с именем `TestInterface` в `Module1`, введя `Interface TestInterface` между инструкциями `Module` и `End Module` и нажав клавишу ВВОД. **Редактор кода** делает отступ для ключевого слова `Interface` и добавляет оператор `End Interface` для формирования блока кода.  
  
5. Определите свойство, метод и событие для интерфейса, поместив следующий код между операторами `Interface` и `End Interface`:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Реализация

 Вы можете заметить, что синтаксис, используемый для объявления членов интерфейса, отличается от синтаксиса, используемого для объявления членов класса. Это различие отражает тот факт, что интерфейсы не могут содержать код реализации.  
  
### <a name="to-implement-the-interface"></a>Реализация интерфейса
  
1. Добавьте класс с именем `ImplementationClass`, добавив следующую инструкцию в `Module1`, после инструкции `End Interface`, но перед инструкцией `End Module` и нажав клавишу ВВОД:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     При работе в интегрированной среде разработки **Редактор кода** предоставляет соответствующую инструкцию `End Class` при нажатии клавиши ВВОД.  
  
2. Добавьте следующую инструкцию `Implements` в `ImplementationClass`, которая именует интерфейс, реализуемый классом:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     При указании отдельно от других элементов в верхней части класса или структуры оператор `Implements` указывает, что класс или структура реализуют интерфейс.  
  
     При работе в интегрированной среде разработки **Редактор кода** реализует члены класса, необходимые для `TestInterface` при нажатии клавиши ВВОД, и можно пропустить следующий шаг.  
  
3. Если вы не работаете в интегрированной среде разработки, необходимо реализовать все члены интерфейса `MyInterface`. Добавьте следующий код `ImplementationClass` для реализации `Event1`, `Method1`и `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     `Implements` оператор именует интерфейс и член интерфейса, который реализуется.  
  
4. Завершите определение `Prop1`, добавив закрытое поле в класс, который сохранил значение свойства:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Возврат значения `pval` из метода доступа get свойства.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Задайте значение `pval` в методе доступа к набору свойств.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. Завершите определение `Method1`, добавив следующий код.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>Тестирование реализации интерфейса
  
1. Щелкните правой кнопкой мыши форму запуска проекта в **Обозреватель решений**и выберите пункт **Просмотреть код**. Редактор отображает класс для начальной формы. По умолчанию форма запуска называется `Form1`.  
  
2. Добавьте следующее поле `testInstance` в класс `Form1`:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Объявляя `testInstance` как `WithEvents`, класс `Form1` может управлять его событиями.  
  
3. Добавьте следующий обработчик событий в класс `Form1` для обработки событий, вызванных `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. Добавьте подпрограммы с именем `Test` в класс `Form1`, чтобы протестировать класс реализации:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     `Test` процедура создает экземпляр класса, который реализует `MyInterface`, присваивает этот экземпляр полю `testInstance`, устанавливает свойство и запускает метод через интерфейс.  
  
5. Добавьте код для вызова процедуры `Test` из `Form1 Load` процедуры формы запуска:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. Выполните `Test` процедуру, нажав клавишу F5. Отображается сообщение «Prop1 имело значение 9». После нажатия кнопки ОК отображается сообщение "параметр X для Method1 равен 5". Нажмите кнопку ОК, после чего появится сообщение "обработчик событий захватил событие".  
  
## <a name="see-also"></a>См. также

- [Оператор Implements](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [Интерфейсы](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Оператор Interface](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md)
