---
title: "Основы разработки приложений Windows Forms (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7872d3c7b19ec9cd7059cccf41e5fab50d85123b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="windows-forms-application-basics-visual-basic"></a>Основы разработки приложений Windows Forms (Visual Basic)
Важной частью [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] является возможность создания приложений Windows Forms, выполняемых локально на пользовательских компьютерах. Visual Studio можно использовать для создания приложений и пользовательский интерфейс, с помощью Windows Forms. Приложение Windows Forms строится на основе классов из <xref:System.Windows.Forms> пространства имен.  
  
## <a name="designing-windows-forms-applications"></a>Приложения проектирование Windows Forms  
 Можно создать в Windows Forms и приложения служб Windows с [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]. Дополнительные сведения см. в следующих разделах:  
  
-   [Приступая к работе с Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Предоставляет сведения о создании и программировании Windows Forms.  
   
-   [Элементы управления Windows Forms](../../../framework/winforms/controls/index.md). Набор разделов, подробно описывающих использование элементов управления Windows Forms.  
  
-   [Приложения служб Windows](../../../framework/windows-services/index.md). Список разделов, в которых описаны способы создания службы Windows.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Построение многофункциональных интерактивных пользовательских интерфейсов  
 Windows Forms — это компонент интеллектуальных клиентов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], набор управляемых библиотек для выполнения распространенных задач, таких как чтение и запись в файловой системе. В среде разработки, такие как [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], можно создать приложения Windows Forms, которые отображают сведения, запрашивают ввод от пользователей и обмениваются данными с удаленными компьютерами по сети.  
  
 В Windows Forms формы — это видимая поверхность, на которой отображается информация для пользователя. Вы часто Windows Forms строится путем помещения элементов управления в формах и написания кода для реагирования на действия пользователя, такие как щелчки мыши или нажатия клавиш. *Элемент управления* — это отдельный элемент пользовательского интерфейса, предназначенный для отображения или ввода данных.  
  
### <a name="events"></a>События  
 Когда пользователь выполняет что-то с формой или одним из ее элементов управления, создается событие. Приложение реагирует на эти события с помощью кода и обрабатывает события при их возникновении. Подробнее см. в разделе [Создание обработчиков событий в Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
### <a name="controls"></a>Элементы управления  
 Windows Forms включает широкий набор элементов управления, которые можно размещать на формах: элементы управления, отображающие текстовые поля, кнопки, раскрывающиеся списки, переключатели и даже веб-страницы. Список всех элементов управления, которые можно использовать в форме, представлены в разделе [Элементы управления для использования в формах Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Если существующий элемент управления не удовлетворяет потребностям, в Windows Forms можно создать пользовательские элементы управления с помощью класса <xref:System.Windows.Forms.UserControl>.  
  
 В состав Windows Forms входят многофункциональные элементы пользовательского интерфейса, позволяющие воссоздавать возможности таких сложных приложений, как Microsoft Office. С помощью <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.MenuStrip> элемента управления, можно создать панели инструментов и меню, содержащие текст и рисунки, подменю и другие элементы управления, такие как текстовые поля и поля со списком.  
  
 С [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] конструктора и перетащите forms можно легко создавать приложения Windows Forms: достаточно выделить элемент управления курсором и поместить их в нужное место на форме. Конструктор предоставляет средства, такие как линии сетки и «линии привязки» для преодоления трудностей выравнивания элементов управления. И при использовании [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] и при компиляции из командной строки можно использовать <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> и <xref:System.Windows.Forms.SplitContainer> элементы управления для создания сложных макетов с минимальными затратами времени и усилий форм.  
  
### <a name="custom-ui-elements"></a>Элементы пользовательского интерфейса  
 Наконец, если необходимо создать свои собственные элементы пользовательского интерфейса, <xref:System.Drawing> пространство имен содержит все классы, необходимые для отрисовки линий, кругов и других фигур непосредственно на форме.  
  
 Пошаговые инструкции по использованию этих функций см. в следующих разделах справки.  
  
|Кому|См.|  
|--------|---------|  
|Создайте новое приложение Windows Forms с помощью[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]|[Пошаговое руководство: Создание простого Windows Form](http://msdn.microsoft.com/library/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Использование элементов управления в формах|[Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|   
|Создание рисунков с помощью<xref:System.Drawing>|[Приступая к программированию графики](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|Создание пользовательских элементов управления|[Практическое руководство. Наследование класса UserControl](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
## <a name="displaying-and-manipulating-data"></a>Отображение и обработка данных  
 Во многих приложениях нужно отображать данные из базы данных, XML-файла, веб-службы XML или другого источника данных. Windows Forms предоставляет гибкий элемент управления называется <xref:System.Windows.Forms.DataGridView> элемента управления для отображения таких табличных данных в традиционном формате строк и столбцов, чтобы каждый фрагмент данных занимает свою собственную ячейку. С помощью <xref:System.Windows.Forms.DataGridView> можно настроить внешний вид отдельных ячеек, зафиксировать строки и столбцы на своем месте и отображение сложных элементов управления внутри ячеек, помимо прочего.  
  
 При использовании интеллектуальных клиентов Windows Forms можно легко подключаться к источникам данных по сети. Компонент Windows Forms <xref:System.Windows.Forms.BindingSource>, появившийся в [!INCLUDE[vsprvslong](~/includes/vsprvslong-md.md)] и [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)], представляет подключение к источнику данных и содержит методы для привязки данных к элементам управления, перехода к предыдущей или следующей записи, редактирования записей и сохранения изменений в исходном источнике. Элемент управления <xref:System.Windows.Forms.BindingNavigator> предоставляет простой интерфейс на основе компонента <xref:System.Windows.Forms.BindingSource> для перехода между записями.  
  
### <a name="data-bound-controls"></a>Элементы управления с привязкой к данным  
 Можно создать элементы управления с привязкой к данным, легко с помощью окна "Источники данных", отображающий источников данных, таких как базы данных, веб-служб и объектов в проекте. Создавать элементы управления с привязкой к данным можно путем перетаскивания объектов из этого окна в формы проекта. Также можно связывать существующие элементы управления с данными, перетаскивая объекты из окна "Источники данных" в существующие элементы управления.  
  
### <a name="settings"></a>Параметры  
 Другой тип привязки данных, которыми можно управлять в Windows Forms — параметры. Большинство интеллектуальных клиентских приложений необходимо сохранять некоторые сведения об их состоянии времени выполнения, такие как последние известные размеры форм и сохранять пользовательские настройки данных, например место сохранения файлов по умолчанию. Параметры приложения отвечает этим требованиям, предоставляя простой способ хранения обоих типов параметров на клиентском компьютере. Определенные один раз с помощью [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] или редактора кода, эти параметры сохраняются в XML-ФАЙЛЕ и автоматически считываются обратно в память во время выполнения.  
  
 Пошаговые инструкции по использованию этих функций см. в следующих разделах справки.  
  
|Кому|См.|  
|--------|---------|  
|Используйте <xref:System.Windows.Forms.BindingSource> компонента|[Практическое руководство. Связывание элементов управления Windows Forms с компонентом BindingSource с помощью конструктора](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|Работать с [!INCLUDE[vstecado](~/includes/vstecado-md.md)] источники данных|[Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|Используйте окно "Источники данных"|[Пошаговое руководство. Отображение данных на форме в приложении Windows](/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Развертывание приложений на клиентских компьютерах  
 После написания приложения необходимо отправить его пользователям, чтобы они могли установить и запустить его на своих клиентских компьютерах. С помощью [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] технологии, можно развернуть приложение из среды [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] с помощью всего нескольких щелчков и предоставлять пользователям URL-адрес приложения в Интернете. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]управляет всеми элементами и зависимостями в приложении и гарантирует, что приложение правильно установлен на клиентском компьютере.  
  
 Приложения [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] можно настроить так, чтобы они работали только при подключении к сети или как в сетевом, так и в автономном режиме. При указании, что приложение должно поддерживать работу в автономном режиме, [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] добавляет ссылку на приложение в каталоге пользователя **запустить** меню, чтобы пользователь смог открыть его без использования URL-адрес.  
  
 Когда вы обновляете приложение, на веб-сервере публикуется новый манифест развертывания и новая копия приложения. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]обнаруживает, что доступно обновление и обновляет пользовательскую установку. для обновления старых сборок написание специального требуется.  
  
 Общие сведения о [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] можно найти в разделе [Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Пошаговые инструкции по использованию этих функций см. в следующих разделах справки:  
  
|Кому|См.|  
|--------|---------|  
|Развертывание приложения с[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Практическое руководство. Публикация приложения ClickOnce с помощью мастера публикации](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Разбор примера: развертывание вручную приложения ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Обновление [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] развертывания|[Практическое руководство. Управление обновлениями для ClickOnce-приложения](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Управление безопасностью с[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Практическое руководство. Включение параметров безопасности ClickOnce-приложений](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Другие элементы управления и возможности  
 В Windows Forms имеется множество других возможностей, которые упрощают и ускоряют реализацию общих задач, таких как создание диалоговых окон, печать, добавление справки и документации, а также локализация приложений на различных языках. Кроме того, Windows Forms применяется эффективная система безопасности [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], что позволяет более надежные приложения для ваших клиентов.  
  
 Пошаговые инструкции по использованию этих функций см. в следующих разделах справки:  
  
|Кому|См.|  
|--------|---------|  
|Печать содержимого формы|[Практическое руководство. Печать графических изображений в Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|   
|Дополнительные сведения о безопасности форм Windows Forms|[Общие сведения о безопасности в Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Общие сведения о Windows Forms](../../../framework/winforms/windows-forms-overview.md)  
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
