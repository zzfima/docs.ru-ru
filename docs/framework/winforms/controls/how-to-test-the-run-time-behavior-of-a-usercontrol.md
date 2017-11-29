---
title: "Практическое руководство. Тестирование поведения элемента UserControl во время выполнения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ce4f821a7b964b3ed2e03c795346b47bb88d618
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Практическое руководство. Тестирование поведения элемента UserControl во время выполнения
При разработке <xref:System.Windows.Forms.UserControl>, необходимо проверить его поведение во время выполнения. Можно создать проект отдельные приложения на основе Windows и разместить элемент управления в тестовую форму, но эта процедура неудобно. Более быстрым и удобным способом является использование **тестовый контейнер пользовательских элементов управления** , предоставляемые Visual Studio. Тестовый контейнер запускается непосредственно из проекта библиотеки элементов управления Windows.  
  
> [!IMPORTANT]
>  К контейнеру теста для загрузки вашей <xref:System.Windows.Forms.UserControl>, элемент управления должен иметь по крайней мере один открытый конструктор.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!NOTE]
>  Элемент управления Visual C++ не может быть проверен с использованием **тестовый контейнер пользовательских элементов управления**.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>Для тестирования поведения элемента UserControl во время выполнения  
  
1.  Создайте проект библиотеки элементов управления Windows вызывается **TestContainerExample**. Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.Label> управления из **элементов** область конструктора элемента управления.  
  
3.  Нажмите клавишу F5, чтобы построить проект и запустить **тестовый контейнер пользовательских элементов управления**. Тестовый контейнер будет отображаться с вашей <xref:System.Windows.Forms.UserControl> в **предварительного просмотра** области.  
  
4.  Выберите <xref:System.Windows.Forms.Control.BackColor%2A> свойства, отображенного в <xref:System.Windows.Forms.PropertyGrid> управления справа от **предварительного просмотра** области. Измените его значение на `ControlDark`. Обратите внимание, что элемента управления изменяется в более темным цветом. Попробуйте изменять другие значения свойства и действие на элементе управления.  
  
5.  Нажмите кнопку **окно** расположенный ниже флажок **предварительного просмотра** области. Обратите внимание, что размер для заполнения области. Измените размер тестового контейнера и обратите внимание, что элемент управления при изменении размеров области.  
  
6.  Закройте тестовый контейнер.  
  
7.  Добавьте другой пользовательский элемент управления для **TestContainerExample** проекта. Дополнительные сведения см. в разделе [NIB: Практическое: Добавление существующих элементов в проект](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
8.  В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.Button> управления из **элементов** область конструктора элемента управления.  
  
9. Нажмите клавишу F5 для построения проекта и запуска тестового контейнера.  
  
10. Нажмите кнопку **выберите пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox> для переключения между двумя элементами управления.  
  
## <a name="testing-user-controls-from-another-project"></a>Тестирование пользовательского элемента управления из другого проекта  
 Пользовательские элементы управления из других проектов, можно проверить в тестовом контейнере текущего проекта.  
  
#### <a name="to-test-user-controls-from-another-project"></a>Для проверки пользовательских элементов управления из другого проекта  
  
1.  Создайте проект библиотеки элементов управления Windows вызывается **TestContainerExample2**. Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.RadioButton> управления из **элементов** область конструктора элемента управления.  
  
3.  Нажмите клавишу F5 для построения проекта и запуска тестового контейнера. Тестовый контейнер будет отображаться с вашей <xref:System.Windows.Forms.UserControl> в **предварительного просмотра** области.  
  
4.  Нажмите кнопку **нагрузки** кнопки.  
  
5.  В **откройте** диалоговом окне перейдите к **TestContainerExample**DLL-файл, который создан в предыдущей процедуре. Выберите **TestContainerExample**DLL-файл и нажмите кнопку **откройте** кнопку, чтобы загрузить пользовательские элементы управления  
  
6.  Используйте **выберите пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox> для переключения между двумя элементами управления из **TestContainerExample** проекта.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.UserControl>  
 [Практическое руководство. Создание составных элементов управления](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [Пошаговое руководство. Создание составного элемента управления с помощью Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Пошаговое руководство. Создание составного элемента управления с помощью C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [Конструктор пользовательских элементов управления](http://msdn.microsoft.com/en-us/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
