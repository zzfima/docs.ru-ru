---
title: "Пошаговое руководство. Определение классов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "модули класса, пошаговые руководства"
  - "классы [Visual Basic], пошаговые руководства"
  - "код, выход"
  - "выполнение, завершение"
  - "выполнение, остановка"
  - "файлы, закрытие"
  - "Initialize - событие"
  - "объекты [Visual Basic], создание"
  - "объекты [Visual Basic], инициализация"
  - "завершение программы"
  - "программы, выход"
  - "Terminate - событие"
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Пошаговое руководство. Определение классов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В данном пошаговом руководстве подробно рассказано, как определить классы, на основе которых впоследствии можно создать объекты.  Здесь также показано, как добавить свойства и методы в новый класс и как инициализировать объект.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Определение класса  
  
1.  Создайте проект; для этого в меню **Файл** щелкните **Создать проект**.  Откроется диалоговое окно **Новый проект**.  
  
2.  Выберите приложение Windows из списка шаблонов проектов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для отображения нового проекта.  
  
3.  Добавьте в проект новый класс; для этого в меню **Проект** щелкните **Добавление класса**.  Открывается диалоговое окно **Добавление нового элемента**.  
  
4.  Выберите шаблон **Класс**.  
  
5.  Назовите новый класс `UserNameInfo.vb` и нажмите кнопку **Добавить**, чтобы отобразить код для нового класса.  
  
     [!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  Можно использовать [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] **Редактор кода**, чтобы добавить класс в форму запуска; для этого введите ключевое слово `Class`, следом за которым укажите имя нового класса.  **Редактор кода** предоставляет соответствующий оператор `End Class`.  
  
6.  Определите закрытое поле для класса, добавив следующий код между операторами `Class` и `End Class`:  
  
     [!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     Объявление полей как `Private` означает, что они могут использоваться только внутри класса.  Можно сделать поля доступными извне класса с помощью модификаторов доступа, например `Public`, которые обеспечивают дополнительный доступ.  Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Определите свойство для класса, добавив следующий код:  
  
     [!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  Определите метод для класса, добавив следующий код:  
  
     [!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. Определите параметризованный конструктор для нового класса, добавив процедуру `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     Конструктор `Sub New` вызывается автоматически при создании объекта на основе данного класса.  Этот конструктор задает значение поля, в котором содержится имя пользователя.  
  
### Создание кнопки для тестирования класса  
  
1.  Переключите форму запуска в режим конструктора; для этого щелкните правой кнопкой мыши ее название в **обозревателе решений**, а затем выберите команду **Конструктор представлений**.  По умолчанию форма запуска для проектов приложений Windows называется Form1.vb.  Затем появится главная форма.  
  
2.  Добавьте в главную форму кнопку и дважды щелкните ее, чтобы отобразить код обработчика событий `Button1_Click`.  Добавьте следующий код, чтобы вызвать процедуру тестирования:  
  
     [!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### Запуск приложения  
  
1.  Запустите приложение, нажав клавишу F5.  Нажмите кнопку в форме, чтобы вызвать процедуру тестирования.  Отображается сообщение, в котором указано, что `UserName` имеет исходное значение "MOORE, BOBBY", поскольку процедурой вызван метод `Capitalize` объекта.  
  
2.  Нажмите кнопку **ОК**, чтобы закрыть окно сообщения.  В процедуре `Button1 Click` изменяется значение свойства `UserName` и отображается сообщение о том, что свойство `UserName` получает новое значение "Worden, Joe".  
  
## См. также  
 [Объектно\-ориентированное программирование](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)   
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)