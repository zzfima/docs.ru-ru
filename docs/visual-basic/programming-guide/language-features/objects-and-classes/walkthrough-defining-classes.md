---
title: Определение классов (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 679f4fd55f142c2c4bb63a556feb95c074960b12
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914736"
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Пошаговое руководство. Определение классов (Visual Basic)

В этом пошаговом руководстве показано, как определить классы, которые затем можно использовать для создания объектов. В нем также показано, как добавить свойства и методы в новый класс, и демонстрируется инициализация объекта.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>Определение класса
  
1. Создайте проект, щелкнув **создать проект** в меню **файл** . Откроется диалоговое окно **Новый проект** .  
  
2. Выберите приложение Windows в списке шаблонов проектов Visual Basic, чтобы отобразить новый проект.  
  
3. Добавьте в проект новый класс, щелкнув **Добавить класс** в меню **проект** . Откроется диалоговое окно **Добавление нового элемента**.  
  
4. Выберите шаблон **класса** .  
  
5. Присвойте новому классу `UserNameInfo.vb`имя, а затем нажмите кнопку **добавить** , чтобы отобразить код для нового класса.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > Можно использовать **Редактор кода** Visual Basic, чтобы добавить класс в форму запуска, введя `Class` ключевое слово, за которым следует имя нового класса. **Редактор кода** предоставляет соответствующий `End Class` оператор.  
  
6. Определите частное поле для класса, добавив следующий код между `Class` операторами и: `End Class`  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Объявление поля как означает, `Private` что его можно использовать только в пределах класса. Можно сделать поля доступными извне класса, используя модификаторы доступа, такие как `Public` , которые обеспечивают дополнительный доступ. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7. Определите свойство для класса, добавив следующий код:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. Определите метод для класса, добавив следующий код:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Определите параметризованный конструктор для нового класса, добавив процедуру с именем `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     `Sub New` Конструктор вызывается автоматически при создании объекта на основе этого класса. Этот конструктор задает значение поля, в котором содержится имя пользователя.  
  
## <a name="to-create-a-button-to-test-the-class"></a>Создание кнопки для проверки класса
  
1. Измените форму запуска на режим конструктора, щелкнув правой кнопкой мыши ее имя в **Обозреватель решений** а затем выбрав пункт **Конструктор представлений**. По умолчанию форма запуска для проектов приложений Windows называется Form1. vb. Откроется Главная форма.  
  
2. Добавьте кнопку в главную форму и дважды щелкните ее, чтобы отобразить код для `Button1_Click` обработчика событий. Добавьте следующий код для вызова тестовой процедуры:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>Запуск приложения
  
1. Запустите приложение, нажав клавишу F5. Нажмите кнопку в форме, чтобы вызвать процедуру тестирования. В нем отображается сообщение о том, что `UserName` исходное значение — «перебобби», поскольку процедура `Capitalize` вызвала метод объекта.  
  
2. Нажмите кнопку **ОК**, чтобы закрыть окно сообщения. Процедура изменяет значение `UserName` свойства и отображает сообщение `UserName` о том, что новое значение равно "Ворден, Джо". `Button1 Click`  
  
## <a name="see-also"></a>См. также

- [Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)
- [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
