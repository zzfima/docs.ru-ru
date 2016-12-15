---
title: "Основы разработки приложений Windows Forms (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "приложения Windows"
  - "Windows Forms, Visual Basic"
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Основы разработки приложений Windows Forms (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Важной особенностью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] является возможность создания приложений Windows Forms, выполняемых локально на пользовательских компьютерах.  Visual Studio можно использовать для создания приложения и пользовательского интерфейса с помощью Windows Forms.  Приложение Windows Forms построено на основе классов из пространства имен <xref:System.Windows.Forms>.  
  
## Проектирование приложений Windows Forms  
 С помощью [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] можно создавать приложения Windows Forms и служб Windows.  Дополнительные сведения см. в следующих разделах.  
  
-   [Getting Started with Windows Forms](../Topic/Getting%20Started%20with%20Windows%20Forms.md).  Сведения о создании и программировании приложений Windows Forms.  
  
-   [Windows Forms Walkthroughs](http://msdn.microsoft.com/ru-ru/fd44d13d-4733-416f-aefc-32592e59e5d9).  Список разделов, содержащих пошаговые описания разработки обычных приложений Windows на основе Windows Forms.  
  
-   [Элементы управления Windows Forms](../Topic/Windows%20Forms%20Controls.md).  Список разделов, подробно описывающих использование элементов управления Windows Forms.  
  
-   [Windows Service Applications](../Topic/Developing%20Windows%20Service%20Applications.md).  Список разделов, в которых описаны способы создания службы Windows.  
  
## Построение многофункциональных интерактивных пользовательских интерфейсов  
 Windows Forms является интеллектуальным клиентским компонентом [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], представляющим собой набор управляемых библиотек для выполнения распространенных задач приложений, например чтения или записи в файловую систему.  С помощью такой среды разработки как [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] можно создавать приложения Windows Forms, которые отображают информацию, запрашивают ввод от пользователей и обмениваются данными с удаленными компьютерами по сети.  
  
 В приложении Windows Forms форма является визуальной областью, в которой отображается информация для пользователя.  Как правило, создание приложения Windows Forms происходит путем добавления в форму элементов управления и написанием ответов на действия пользователя, такие как щелчки мыши или нажатия клавиш.  *Элемент управления* — это отдельный элемент пользовательского интерфейса, предназначенный для отображения или ввода данных.  
  
### События  
 Когда пользователь выполняет какое\-либо действие с формой или одним из ее элементов управления, создается событие.  Приложение реагирует на эти события с помощью кода и обрабатывает события при их возникновении.  Дополнительные сведения см. в разделе [Creating Event Handlers in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md).  
  
### Элементы управления  
 Windows Forms включает широкий набор элементов управления, которые можно добавлять в формы: текстовые поля, кнопки, раскрывающиеся списки, переключатели и даже веб\-страницы.  Список всех элементов управления, которые можно использовать в форме, см. в разделе [Элементы управления для использования в формах Windows Forms](../Topic/Controls%20to%20Use%20on%20Windows%20Forms.md).  Если существующий элемент управления не удовлетворяет потребностям, в Windows Forms можно создать собственные пользовательские элементы управления с помощью класса <xref:System.Windows.Forms.UserControl>.  
  
 В состав Windows Forms входят элементы пользовательского интерфейса с расширенными функциями, соответствующими возможностям мощных приложений, таких как Microsoft Office.  Используя элементы управления <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.MenuStrip>, можно создать панели инструментов и меню, содержащие текст и рисунки, отображающие подменю и содержащие в себе другие элементы управления, такие как текстовые поля и поля с выпадающим списком.  
  
 С помощью конструктора форм [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], поддерживающего перетаскивание, можно легко создавать приложения Windows Forms: достаточно выделить элементы управления курсором и поместить их в нужное место на форме.  Такие средства конструктора, как линии сетки и "линии привязки", помогают упростить выравнивание элементов управления.  А в случае использования [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] или компиляции из командной строки можно использовать элементы управления <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> и <xref:System.Windows.Forms.SplitContainer> для создания более сложных макетов форм за минимальное время и с минимальными усилиями.  
  
### Пользовательские элементы интерфейса  
 Наконец, если требуется создать собственные элементы пользовательского интерфейса, можно воспользоваться пространством имен <xref:System.Drawing>, которое содержит все классы, необходимые для отображения линий, кругов и других фигур непосредственно в форме.  
  
 Пошаговые инструкции по использованию этих средств см. в следующих разделах справки.  
  
|Целевой тип|См.|  
|-----------------|---------|  
|Создание нового приложения Windows Forms с помощью [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]|[Walkthrough: Creating a Simple Windows Form](http://msdn.microsoft.com/ru-ru/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Использование элементов управления в формах|[Практическое руководство. Добавление элементов управления в формы Windows Forms.](../Topic/How%20to:%20Add%20Controls%20to%20Windows%20Forms.md)|  
|Обработка событий формы и ее элементов управления|[How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/ru-ru/8461e9b8-14e8-406f-936e-3726732b23d2)|  
|Использование элемента управления <xref:System.Windows.Forms.ToolStrip>|[Практическое руководство. Создание базового элемента управления ToolStrip со стандартными элементами с помощью конструктора](../Topic/How%20to:%20Create%20a%20Basic%20Windows%20Forms%20ToolStrip%20with%20Standard%20Items%20Using%20the%20Designer.md)|  
|Создание рисунков с помощью пространства имен <xref:System.Drawing>|[Приступая к программированию графики](../Topic/Getting%20Started%20with%20Graphics%20Programming.md)|  
|Создание пользовательских элементов управления|[Практическое руководство. Наследование класса UserControl.](../Topic/How%20to:%20Inherit%20from%20the%20UserControl%20Class.md)|  
  
## Отображение и управление данными  
 Во многих приложениях нужно отображать данные из базы данных, XML\-файла, веб\-службы XML или другого источника данных.  Windows Forms предоставляет элемент управления <xref:System.Windows.Forms.DataGridView> с гибкими возможностями для отрисовки таких табличных данных в традиционном формате строк и столбцов таким образом, чтобы каждый элемент данных занимал свою собственную ячейку.  При помощи класса <xref:System.Windows.Forms.DataGridView> можно настроить внешний вид отдельных ячеек, зафиксировать строки и столбцы на своем месте, а также отобразить сложные элементы управления внутри ячеек.  
  
 При использовании интеллектуальных клиентов Windows Forms подключение к источникам данных по сети оказывается простой задачей.  Новый компонент Windows Forms <xref:System.Windows.Forms.BindingSource>, появившийся в [!INCLUDE[vsprvslong](../../../csharp/misc/includes/vsprvslong_md.md)] и [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)], представляет подключение к источнику данных и содержит методы для связывания данных с элементами управления, перехода к предыдущей или следующей записи, редактирования и сохранения изменений в исходном источнике.  Элемент управления <xref:System.Windows.Forms.BindingNavigator> предоставляет простой интерфейс к компоненту <xref:System.Windows.Forms.BindingSource>, предназначенному для перехода между записями.  
  
### Элементы управления с привязкой к данным  
 С помощью окна "Источники данных" можно легко создавать элементы управления с привязкой к данным. В этом окне отображаются источники данных, такие как базы данных, веб\-службы и объекты проекта.  Кроме того, создавать элементы управления с привязкой к данным можно путем перетаскивания элементов из этого окна в формы проекта.  Существующие элементы управления можно связывать с данными путем перетаскивания объектов из окна "Источники данных" на такие элементы управления.  
  
### Параметры  
 Другой тип управления привязкой к данным в формах Windows Forms связан с параметрами.  Большинству интеллектуальных клиентских приложений требуется сохранять некоторые сведения о своем состоянии во время выполнения, такие как последний известный размер форм, а также сохранять ряд пользовательских параметров, таких как расположение сохраняемых файлов по умолчанию.  Функция параметров приложения обеспечивает простой способ хранения обоих типов параметров на клиентском компьютере.  Определенные один раз с помощью [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] или редактора кода, параметры сохраняются в XML\-файле и автоматически считываются обратно в память во время выполнения.  
  
 Пошаговые инструкции по использованию этих средств см. в следующих разделах справки.  
  
|Целевой тип|См.|  
|-----------------|---------|  
|Использование компонента <xref:System.Windows.Forms.BindingSource>|[Практическое руководство. Связывание элементов управления Windows Forms с компонентом BindingSource с помощью конструктора](../Topic/How%20to:%20Bind%20Windows%20Forms%20Controls%20with%20the%20BindingSource%20Component%20Using%20the%20Designer.md)|  
|Работа с источниками данных [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)]|[Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms](../Topic/How%20to:%20Sort%20and%20Filter%20ADO.NET%20Data%20with%20the%20Windows%20Forms%20BindingSource%20Component.md)|  
|Использование окна "Источники данных"|[Пошаговое руководство. Отображение данных на форме в приложении Windows](../Topic/Walkthrough:%20Displaying%20Data%20on%20a%20Windows%20Form.md)|  
|Использование параметров приложения|[How to: Create Application Settings Using the Designer](http://msdn.microsoft.com/ru-ru/53b3af80-1c02-4e35-99c6-787663148945)|  
  
## Развертывание приложений на клиентских компьютерах  
 После создания приложения его нужно отправить пользователям, чтобы они установили и запускали его на собственных клиентских компьютерах.  С помощью технологии [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] можно развертывать приложения в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], только несколько раз нажав кнопку мыши и предоставив пользователям URL\-адрес приложения в Интернете.  [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] управляет всеми элементами и зависимостями в приложении и обеспечивает установку приложения на клиентском компьютере должным образом.  
  
 Приложения [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] можно настроить на выполнение только при условии подключения пользователя к сети, или на выполнение как в интерактивном, так и в автономном режимах.  Когда требуется указать, что приложение поддерживает работу в автономном режиме, [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] добавляет ссылку на приложение в пользовательское меню **Пуск**, так что пользователь сможет открыть его без использования URL\-адреса.  
  
 При обновлении приложения на веб\-сервере публикуется новый манифест развертывания и новая копия приложения.  [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] обнаруживает доступное обновление и выполняет обновление пользовательской установки; для обновления старых сборок не требуется никакого пользовательского программирования.  
  
 Вводные сведения о [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] см. в разделе [Развертывание и безопасность технологии ClickOnce](/visual-studio/deployment/clickonce-security-and-deployment).  Пошаговые инструкции по использованию этих средств см. в следующих разделах справки.  
  
|Целевой тип|См.|  
|-----------------|---------|  
|Развертывание приложения с помощью технологии [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Практическое руководство. Публикация приложения ClickOnce с помощью мастера публикации](../Topic/How%20to:%20Publish%20a%20ClickOnce%20Application%20using%20the%20Publish%20Wizard.md)<br /><br /> [Разбор примера: развертывание вручную приложения ClickOnce](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md)|  
|Обновление развертывания [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Практическое руководство. Управление обновлениями для ClickOnce\-приложения](../Topic/How%20to:%20Manage%20Updates%20for%20a%20ClickOnce%20Application.md)|  
|Управление безопасностью с помощью [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Практическое руководство. Включение параметров безопасности ClickOnce\-приложений.](../Topic/How%20to:%20Enable%20ClickOnce%20Security%20Settings.md)|  
  
## Другие элементы управления и возможности  
 В Windows Forms имеется множество других возможностей, которые упрощают и ускоряют реализацию общих задач, таких как поддержка создания диалоговых окон, печати, добавления справки и документации и локализации приложений на нескольких языках.  Кроме того, Windows Forms построено на основе надежной системы безопасности [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], что позволяет предлагать заказчикам более безопасные приложения.  
  
 Пошаговые инструкции по использованию этих средств см. в следующих разделах справки.  
  
|Целевой тип|См.|  
|-----------------|---------|  
|Печать содержимого формы|[How to: Print Graphics in Windows Forms](../Topic/How%20to:%20Print%20Graphics%20in%20Windows%20Forms.md)<br /><br /> [How to: Print a Multi\-Page Text File in Windows Forms](../Topic/How%20to:%20Print%20a%20Multi-Page%20Text%20File%20in%20Windows%20Forms.md)|  
|Глобализация приложений Windows Forms|[Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5)|  
|Дополнительные сведения о безопасности форм Windows Forms|[Security in Windows Forms Overview](../Topic/Security%20in%20Windows%20Forms%20Overview.md)|  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Общие сведения о Windows Forms](../Topic/Windows%20Forms%20Overview.md)   
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)