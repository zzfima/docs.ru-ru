---
title: "Определение классов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- execution, ending
- objects [Visual Basic], initializing
- Initialize event
- files, closing
- programs, quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event
- execution, stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aeaa5c2bb85c1a642da15c6a29546cf065380e27
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-defining-classes-visual-basic"></a>Пошаговое руководство. Определение классов (Visual Basic)
В этом пошаговом руководстве показано, как определять классы, которые затем можно использовать для создания объектов. Также показано, как добавить свойства и методы в новый класс и показано, как инициализировать объект.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-a-class"></a>Определение класса  
  
1.  Создайте проект, нажав кнопку **новый проект** на **файл** меню. Откроется диалоговое окно **Новый проект** .  
  
2.  Выберите приложение Windows из списка [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проект шаблоны для отображения нового проекта.  
  
3.  Добавьте новый класс в проект, нажав кнопку **добавить класс** на **проекта** меню. **Add New Item** откроется диалоговое окно.  
  
4.  Выберите **класса** шаблона.  
  
5.  Назовите новый класс `UserNameInfo.vb`, а затем нажмите кнопку **добавить** чтобы отобразить код для нового класса.  
  
     [!code-vb[VbVbalrOOP&#5;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  Можно использовать [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **редактор кода** Чтобы добавить класс в форму запуска, введя `Class` ключевое слово, за которым следует имя нового класса. **Редактор кода** предоставляет соответствующий `End Class` инструкции для вас.  
  
6.  Определите закрытое поле для класса, добавив следующий код между `Class` и `End Class` инструкции:  
  
     [!code-vb[VbVbalrOOP&#7;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     Объявление полей как `Private` означает могут использоваться только внутри класса. Можно сделать поля доступными извне класса с помощью модификаторов доступа, такие как `Public` , обеспечивают дополнительный доступ. Дополнительные сведения см. в разделе [уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Определите свойство класса, добавив следующий код:  
  
     [!code-vb[VbVbalrOOP №&8;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  Определите метод для класса, добавив следующий код:  
  
     [!code-vb[VbVbalrOOP №&9;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. Определите параметризованный конструктор для нового класса, добавив процедуру с именем `Sub New`:  
  
     [!code-vb[VbVbalrOOP&#10;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     `Sub New` Конструктор вызывается автоматически при создании объекта на основе данного класса. Этот конструктор задает значение поля, которое содержит имя пользователя.  
  
### <a name="to-create-a-button-to-test-the-class"></a>Создание кнопки для тестирования класса  
  
1.  Переключите форму запуска в режим конструктора, щелкнув правой кнопкой мыши его имя в **обозревателе решений** и выбрав **конструктор представлений**. По умолчанию форма запуска для проектов приложений Windows называется Form1.vb. Затем появится главная форма.  
  
2.  Добавьте в главную форму кнопку и дважды щелкните его, чтобы отобразить код для `Button1_Click` обработчика событий. Добавьте следующий код, чтобы вызвать процедуру тестирования:  
  
     [!code-vb[VbVbalrOOP&#12;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### <a name="to-run-your-application"></a>Запуск приложения  
  
1.  Запустите приложение, нажав клавишу F5. Нажмите кнопку на форме, чтобы вызвать процедуру тестирования. Будет выведено сообщение о том, что исходный `UserName` — «MOORE, BOBBY», поскольку процедурой вызван `Capitalize` метода объекта.  
  
2.  Щелкните **ОК** чтобы закрыть окно сообщения. `Button1 Click` Процедура изменяет значение `UserName` свойства и отображает сообщение о том, что новое значение `UserName` «Worden, Joe».  
  
## <a name="see-also"></a>См. также  
 [Объектно ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

