---
title: "Создание и реализация интерфейсов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08bf6dc7344d4f83c8ab1908fdeb29eb4a53e142
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Пошаговое руководство. Создание и реализация интерфейсов (Visual Basic)
Интерфейсы описывают характеристики свойств, методов и событий, но оставить сведения о реализации до структур или классов.  
  
 В этом пошаговом руководстве показано, как объявить и реализовать интерфейс.  
  
> [!NOTE]
>  В этом пошаговом руководстве не предоставляет сведения о том, как создавать пользовательский интерфейс.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-an-interface"></a>Определение интерфейса  
  
1.  Откройте новый проект приложения Windows [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
2.  Добавьте в проект новый модуль, щелкнув **добавить модуль** на **проекта** меню.  
  
3.  Назовите новый модуль `Module1.vb` и нажмите кнопку **добавить**. Отображается код для нового модуля.  
  
4.  Определите интерфейс с именем `TestInterface` в `Module1` , введя `Interface TestInterface` между `Module` и `End Module` инструкции и нажмите клавишу ВВОД. **Редактор кода** отступы `Interface` ключевое слово и добавляет `End Interface` инструкции для формирования блока кода.  
  
5.  Определение свойств, методов и событий интерфейса, установив следующий код между `Interface` и `End Interface` инструкции:  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a>Реализация  
 Вы можете заметить, что синтаксис для объявления членов интерфейса отличается от синтаксиса, который используется для объявления членов класса. Это различие отражает тот факт, что интерфейсы не могут содержать код реализации.  
  
#### <a name="to-implement-the-interface"></a>Реализация интерфейса  
  
1.  Добавьте класс с именем `ImplementationClass` , добавив следующую инструкцию, чтобы `Module1`после того, как `End Interface` инструкции перед вызовом `End Module` инструкции и нажмите клавишу ВВОД:  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     При работе в интегрированной среде разработки, **редактор кода** подставит соответствующий `End Class` инструкция, при нажатии клавиши ВВОД.  
  
2.  Добавьте следующие `Implements` инструкции `ImplementationClass`, который определяет реализуемый класс реализует:  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     Указанный отдельно от других элементов в верхней части класса или структуры, `Implements` инструкция указывает, что класс или структура реализуют интерфейс.  
  
     При работе в интегрированной среде разработки, **редактор кода** реализует члены класса, необходимые `TestInterface` при нажатии клавиши ВВОД, и следующий шаг можно пропустить.  
  
3.  Если вы работаете не в интегрированной среде разработки, необходимо реализовать все члены интерфейса `MyInterface`. Добавьте следующий код в `ImplementationClass` реализовать `Event1`, `Method1`, и `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     `Implements` Инструкция имена интерфейсов и реализации члена интерфейса.  
  
4.  Завершите определение `Prop1` путем добавления закрытое поле для класса, который хранится значение свойства:  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     Возвращает значение `pval` из свойства метод доступа get.  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     Установите для параметра `pval` метод доступа set свойства.  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  Завершите определение `Method1` , добавив следующий код.  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a>Чтобы проверить реализацию интерфейса  
  
1.  Щелкните правой кнопкой мыши форму запуска проекта в **обозревателе решений**и нажмите кнопку **Просмотр кода**. Редактор отображает класс формы запуска. По умолчанию форма запуска называется `Form1`.  
  
2.  Добавьте следующие `testInstance` на `Form1` класса:  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     Объявив `testInstance` как `WithEvents`, `Form1` класс может обрабатывать события.  
  
3.  Добавьте следующий обработчик событий `Form1` класса для обработки событий, вызванных `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  Добавить подпрограмму с именем `Test` для `Form1` класс, чтобы протестировать класс реализации:  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     `Test` Процедура используется для создания экземпляра класса, который реализует `MyInterface`, присваивает этот экземпляр `testInstance` поля, задает свойство и запускает метод через интерфейс.  
  
5.  Добавьте код для вызова `Test` процедуры из `Form1 Load` процедуры при запуске формы:  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  Запустите `Test` процедуры, нажав клавишу F5. Отображается сообщение «Prop1 было задано значение 9». После нажатия кнопки ОК, сообщение «параметр для метода Method1 X равно 5» отображается. Нажмите "ОК" и отображается сообщение «обработчик событий обнаружено событие».  
  
## <a name="see-also"></a>См. также  
 [Оператор Implements](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Интерфейсы](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Оператор Interface](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md)
