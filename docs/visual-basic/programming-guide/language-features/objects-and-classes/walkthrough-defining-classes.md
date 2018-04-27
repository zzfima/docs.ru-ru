---
title: Определение классов (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fc173ad853755c4b02a13abc0a80229bebffe64
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Пошаговое руководство. Определение классов (Visual Basic)

В этом пошаговом руководстве показано, как определить классы, которые затем можно использовать для создания объектов. Также показано, как добавлять свойства и методы в новый класс и показано, как инициализировать объект.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>Определение класса
  
1.  Создайте проект, щелкнув **новый проект** на **файл** меню. Откроется диалоговое окно **Новый проект** .  
  
2.  Выберите приложение Windows из списка шаблонов проектов Visual Basic для отображения нового проекта.  
  
3.  Добавьте новый класс в проект, щелкнув **добавить класс** на **проекта** меню. Откроется диалоговое окно **Добавление нового элемента**.  
  
4.  Выберите **класса** шаблона.  
  
5.  Имя для нового класса `UserNameInfo.vb`, а затем нажмите кнопку **добавить** для отображения в код для нового класса.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  В Visual Basic можно использовать **редактор кода** Чтобы добавить класс в форму запуска, введя `Class` ключевое слово, за которым следует имя нового класса. **Редактор кода** предоставляет соответствующий `End Class` инструкции для вас.  
  
6.  Определите закрытое поле для класса, добавив следующий код между `Class` и `End Class` инструкции:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Объявление полей как `Private` означает, он может использоваться только внутри класса. Можно сделать поля доступными извне класса с помощью модификаторов доступа, таких как `Public` , обеспечивающие более высокий уровень доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Определите свойства для класса, добавив следующий код:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  Определите метод для класса, добавив следующий код:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Определите параметризованный конструктор для нового класса, добавив процедуру с именем `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     `Sub New` Конструктор вызывается автоматически при создании объекта на основе данного класса. Этот конструктор задает значение поля, которое содержит имя пользователя.  
  
## <a name="to-create-a-button-to-test-the-class"></a>Создание кнопки для тестирования класса
  
1.  Изменить форму запуска в режим конструктора, щелкните правой кнопкой мыши его имя в **обозревателе решений** и выбрав **конструктор представлений**. По умолчанию форма запуска для проектов приложений Windows с именем Form1.vb. Затем появится главная форма.  
  
2.  Добавьте в главную форму кнопку и дважды щелкните его, чтобы открыть код `Button1_Click` обработчика событий. Добавьте следующий код, чтобы вызвать процедуру тестирования:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>Запуск приложения
  
1.  Запустите приложение, нажав клавишу F5. Нажмите кнопку на форме, чтобы вызвать процедуру тестирования. Будет выведено сообщение о том, что исходный `UserName` — «MOORE, BOBBY», поскольку процедурой вызван `Capitalize` метод объекта.  
  
2.  Нажмите кнопку **ОК** , чтобы закрыть окно сообщения. `Button1 Click` Процедура изменяет значение `UserName` свойства и отображает сообщение о том, что новое значение `UserName` «Worden, Joe».  
  
## <a name="see-also"></a>См. также

[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)  
[Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)