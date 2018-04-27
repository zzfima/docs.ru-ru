---
title: Создание и реализация интерфейсов (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0368207e0bda6e0e003ecd7988b77d765c7edc37
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Пошаговое руководство. Создание и реализация интерфейсов (Visual Basic)

Интерфейсы описывают характеристики свойств, методов и событий, но оставить сведения о реализации до структур или классов.  
  
 В этом пошаговом руководстве показано, как объявить и реализовать интерфейс.  
  
> [!NOTE]
>  В этом пошаговом руководстве не предоставляет сведения о том, как создавать пользовательский интерфейс.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Определение интерфейса
  
1.  Откройте новый проект приложения Windows в Visual Basic.  
  
2.  Добавьте в проект новый модуль, щелкнув **добавить модуль** на **проекта** меню.  
  
3.  Назовите новый модуль `Module1.vb` и нажмите кнопку **добавить**. Отображается код для нового модуля.  
  
4.  Определите интерфейс с именем `TestInterface` в `Module1` , введя `Interface TestInterface` между `Module` и `End Module` инструкции и нажмите клавишу ВВОД. **Редактор кода** отступы `Interface` ключевое слово и добавляет `End Interface` инструкции для формирования блока кода.  
  
5.  Определение свойств, методов и событий интерфейса, установив следующий код между `Interface` и `End Interface` инструкции:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Реализация

 Вы можете заметить, что синтаксис для объявления членов интерфейса отличается от синтаксиса, который используется для объявления членов класса. Это различие отражает тот факт, что интерфейсы не могут содержать код реализации.  
  
### <a name="to-implement-the-interface"></a>Реализация интерфейса
  
1.  Добавьте класс с именем `ImplementationClass` , добавив следующую инструкцию, чтобы `Module1`после того, как `End Interface` инструкции перед вызовом `End Module` инструкции и нажмите клавишу ВВОД:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     При работе в интегрированной среде разработки, **редактор кода** подставит соответствующий `End Class` инструкция, при нажатии клавиши ВВОД.  
  
2.  Добавьте следующие `Implements` инструкции `ImplementationClass`, который определяет реализуемый класс реализует:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Указанный отдельно от других элементов в верхней части класса или структуры, `Implements` инструкция указывает, что класс или структура реализуют интерфейс.  
  
     При работе в интегрированной среде разработки, **редактор кода** реализует члены класса, необходимые `TestInterface` при нажатии клавиши ВВОД, и следующий шаг можно пропустить.  
  
3.  Если вы работаете не в интегрированной среде разработки, необходимо реализовать все члены интерфейса `MyInterface`. Добавьте следующий код в `ImplementationClass` реализовать `Event1`, `Method1`, и `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     `Implements` Инструкция имена интерфейсов и реализации члена интерфейса.  
  
4.  Завершите определение `Prop1` путем добавления закрытое поле для класса, который хранится значение свойства:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Возвращает значение `pval` из свойства метод доступа get.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Установите для параметра `pval` метод доступа set свойства.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  Завершите определение `Method1` , добавив следующий код.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>Чтобы проверить реализацию интерфейса
  
1.  Щелкните правой кнопкой мыши форму запуска проекта в **обозревателе решений**и нажмите кнопку **Просмотр кода**. Редактор отображает класс формы запуска. По умолчанию форма запуска называется `Form1`.  
  
2.  Добавьте следующие `testInstance` на `Form1` класса:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Объявив `testInstance` как `WithEvents`, `Form1` класс может обрабатывать события.  
  
3.  Добавьте следующий обработчик событий `Form1` класса для обработки событий, вызванных `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  Добавить подпрограмму с именем `Test` для `Form1` класс, чтобы протестировать класс реализации:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     `Test` Процедура используется для создания экземпляра класса, который реализует `MyInterface`, присваивает этот экземпляр `testInstance` поля, задает свойство и запускает метод через интерфейс.  
  
5.  Добавьте код для вызова `Test` процедуры из `Form1 Load` процедуры при запуске формы:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  Запустите `Test` процедуры, нажав клавишу F5. Отображается сообщение «Prop1 было задано значение 9». После нажатия кнопки ОК, сообщение «параметр для метода Method1 X равно 5» отображается. Нажмите "ОК" и отображается сообщение «обработчик событий обнаружено событие».  
  
## <a name="see-also"></a>См. также

 [Оператор Implements](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Интерфейсы](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Оператор Interface](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md)  