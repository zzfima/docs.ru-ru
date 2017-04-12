---
title: "Windows Forms основы разработки приложений (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 8275d3c06ebd89254a07127b4850d32ef0580830
ms.lasthandoff: 03/13/2017

---
# <a name="windows-forms-application-basics-visual-basic"></a>Основы разработки приложений Windows Forms (Visual Basic)
Важной частью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] является возможность создания приложений Windows Forms, локально работающих на компьютерах пользователей. Visual Studio можно использовать для создания приложений и пользовательский интерфейс, с помощью Windows Forms. Приложение Windows Forms строится на основе классов из <xref:System.Windows.Forms>имен.</xref:System.Windows.Forms>  
  
## <a name="designing-windows-forms-applications"></a>Разработка Windows Forms в приложения  
 Можно создать в Windows Forms и приложения служб Windows с [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]. Дополнительные сведения см. в следующих разделах:  
  
-   [Приступая к работе с Windows Forms](https://msdn.microsoft.com/library/ms229601.aspx). Сведения о создании и программировании Windows Forms.  
   
-   [Элементы управления Windows Forms](https://msdn.microsoft.com/library/ettb6e2a.aspx). Набор разделов, подробно описывающих использование элементов управления Windows Forms.  
  
-   [Приложения служб Windows](https://msdn.microsoft.com/library/y817hyb6.aspx). Список разделов, в которых описаны способы создания службы Windows.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Построение многофункциональных интерактивных пользовательских интерфейсов  
 Windows Forms — это компонент смарт клиентов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], набор управляемых библиотек для выполнения распространенных задач, таких как чтение и запись в файловую систему. В среде разработки, такие как [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], можно создавать приложения Windows Forms, которые отображают информацию, запрашивают ввод от пользователей и взаимодействия с удаленными компьютерами по сети.  
  
 В Windows Forms форма является видимая поверхность, на которой отображается информация для пользователя. Обычно создание приложений Windows Forms путем размещения элементов управления в формах и разработки ответов на действия пользователя, такие как щелчки мыши или нажатия клавиш. Объект *управления* — отдельный элемент (UI), предназначенный для отображения или ввода данных.  
  
### <a name="events"></a>События  
 Когда пользователь выполняет что-то с формой или одним из ее элементов управления, создается событие. Приложение реагирует на эти события с помощью кода и обрабатывает события при их возникновении. Дополнительные сведения см. в разделе [Создание обработчиков событий в Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx).  
  
### <a name="controls"></a>Элементы управления  
 Windows Forms включает широкий набор элементов управления, которые можно помещать на формы: элементы управления, отображающие текстовые поля, кнопки, раскрывающиеся списки, переключатели и даже веб-страницы. Список всех элементов управления, которые можно использовать в форме, в разделе [элементы управления для использования в формах Windows Forms](https://msdn.microsoft.com/library/3xdhey7w.aspx). Если существующий элемент управления не удовлетворяет потребностям, Windows Forms можно создавать собственные пользовательские элементы управления с помощью <xref:System.Windows.Forms.UserControl>класса.</xref:System.Windows.Forms.UserControl>  
  
 В состав Windows Forms входят многофункциональные элементы пользовательского интерфейса, позволяющие воссоздавать возможности таких сложных приложений, как Microsoft Office. С помощью <xref:System.Windows.Forms.ToolStrip>и <xref:System.Windows.Forms.MenuStrip>элемента управления, можно создать панели инструментов и меню, содержащие текст и изображения, показывать подменю и размещать другие элементы, такие как текстовые поля и поля со списком.</xref:System.Windows.Forms.MenuStrip> </xref:System.Windows.Forms.ToolStrip>  
  
 С [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] конструктор форм и перетащите можно легко создавать приложения Windows Forms: достаточно выделить элементы управления курсором и поместить их в нужное место на форме. Конструктор предоставляет средства, такие как линии сетки и «линии привязки» для преодоления трудностей выравнивания элементов управления. И при использовании [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] и при компиляции из командной строки можно использовать <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel>и <xref:System.Windows.Forms.SplitContainer>форме элементы управления для создания сложных макетов с минимальными затратами времени и усилий.</xref:System.Windows.Forms.SplitContainer> </xref:System.Windows.Forms.TableLayoutPanel> </xref:System.Windows.Forms.FlowLayoutPanel>  
  
### <a name="custom-ui-elements"></a>Элементы пользовательского интерфейса  
 Наконец, если необходимо создать собственные настраиваемые элементы пользовательского интерфейса <xref:System.Drawing>пространство имен содержит все классы, необходимые для отображения линий, кругов и других фигур непосредственно на форме.</xref:System.Drawing>  
  
 Пошаговые инструкции по использованию этих функций см. в следующих разделах справки.  
  
|Целевой тип|См.|  
|--------|---------|  
|Создание нового приложения Windows Forms с помощью[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]|[Пошаговое руководство: Создание простого Windows Form](http://msdn.microsoft.com/en-us/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Использование элементов управления в формах|[Практическое руководство: Добавление элементов управления в Windows Forms](https://msdn.microsoft.com/library/0h5y8567.aspx)|   
|Создание рисунков с помощью<xref:System.Drawing></xref:System.Drawing>|[Приступая к программированию графики](https://msdn.microsoft.com/library/da0f23z7.aspx)|  
|Создание пользовательских элементов управления|[Практическое руководство: наследование класса UserControl](https://msdn.microsoft.com/library/00ctb4z0.aspx)|  
  
## <a name="displaying-and-manipulating-data"></a>Отображение и обработка данных  
 Во многих приложениях нужно отображать данные из базы данных, XML-файла, веб-службы XML или другого источника данных. Windows Forms предоставляет гибкий элемент управления с именем <xref:System.Windows.Forms.DataGridView>, предназначенный для представления таких табличных данных в традиционном формате строк и столбцов так, что каждый фрагмент данных занимает свою собственную ячейку.</xref:System.Windows.Forms.DataGridView> С помощью <xref:System.Windows.Forms.DataGridView>можно настроить внешний вид отдельных ячеек, зафиксировать строки и столбцы на своем месте и отображение сложных элементов управления внутри ячеек, помимо других функций.</xref:System.Windows.Forms.DataGridView>  
  
 При использовании интеллектуальных клиентов Windows Forms можно легко подключаться к источникам данных по сети. <xref:System.Windows.Forms.BindingSource>Компонент, появившееся в Windows Forms в [!INCLUDE[vsprvslong](../../../csharp/misc/includes/vsprvslong_md.md)] и [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)], представляет собой соединение с источником данных и предоставляет методы для привязки данных к элементам управления, перехода к предыдущей и следующей записи, редактирования записей и сохранения изменений в исходном источнике.</xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingNavigator>Управления предоставляет простой интерфейс на <xref:System.Windows.Forms.BindingSource>компонента для перехода между записями.</xref:System.Windows.Forms.BindingSource> </xref:System.Windows.Forms.BindingNavigator>  
  
### <a name="data-bound-controls"></a>Элементы управления с привязкой к данным  
 Можно создать элементы управления с привязкой к данным с помощью окна "Источники данных", отображающий источников данных, таких как базы данных, веб-службы и объекты в проекте. Создавать элементы управления с привязкой к данным можно путем перетаскивания объектов из этого окна в формы проекта. Также можно связывать существующие элементы управления с данными, перетаскивая объекты из окна "Источники данных" в существующие элементы управления.  
  
### <a name="settings"></a>Параметры  
 Другой тип привязки данных, которыми можно управлять в Windows Forms — это параметры. Большинство приложений интеллектуальных клиентов должны сохранять некоторые сведения о своем состоянии во время выполнения, например последний известный размер форм и сохранять пользовательские настройки, например расположение сохраняемых файлов по умолчанию. Параметры приложения отвечает этим требованиям, предоставляя простой способ хранения обоих типов параметров на клиентском компьютере. Определенные один раз с помощью [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] или редактора кода, эти параметры сохраняются в XML-ФАЙЛЕ и автоматически считываются обратно в память во время выполнения.  
  
 Пошаговые инструкции по использованию этих функций см. в следующих разделах справки.  
  
|Целевой тип|См.|  
|--------|---------|  
|Использование <xref:System.Windows.Forms.BindingSource>компонента</xref:System.Windows.Forms.BindingSource>|[Практическое руководство: привязка элементов управления Windows Forms с компонентом BindingSource с помощью конструктора](https://msdn.microsoft.com/library/801dxw2t.aspx)|  
|Работа с [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] источников данных|[Практическое руководство: сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|Использование окна источников данных|[Пошаговое руководство. Отображение данных на форме в приложении Windows](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Развертывание приложений на клиентских компьютерах  
 После написания приложения необходимо отправить его пользователям, чтобы они могли установить и запустить его на своих клиентских компьютерах. С помощью [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] технологии, можно развернуть приложение из среды [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] , используя всего несколько щелчков и предоставлять пользователям URL-адрес приложения в Интернете. [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]управляет всеми элементами и зависимостями в приложении и обеспечивает установку приложения на клиентском компьютере должным образом.  
  
 Приложения [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] можно настроить так, чтобы они работали только при подключении к сети или как в сетевом, так и в автономном режиме. При указании, что приложение должно поддерживать операции в автономном режиме, [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] добавляет ссылку на приложение в каталоге пользователя **запустить** меню, так что пользователь сможет открыть его без использования URL-адрес.  
  
 Когда вы обновляете приложение, на веб-сервере публикуется новый манифест развертывания и новая копия приложения. [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]обнаруживает наличие обновлений и обновляет пакет установки пользователя; требуется никакого программирования для обновления старых сборок.  
  
 Полное описание [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)], в разделе [развертывание и безопасность технологии ClickOnce](https://docs.microsoft.com/visualstudio/deployment/clickonce-security-and-deployment). Пошаговые инструкции по использованию этих функций см. в следующих разделах справки:  
  
|Целевой тип|См.|  
|--------|---------|  
|Развертывание приложения с[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Практическое руководство. Публикация приложения ClickOnce с помощью мастера публикации](https://docs.microsoft.com/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Разбор примера: развертывание вручную приложения ClickOnce](https://docs.microsoft.com/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Обновление [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] развертывания|[Практическое руководство. Управление обновлениями для ClickOnce-приложения](https://docs.microsoft.com/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Управление безопасностью с помощью[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Практическое руководство. Включение параметров безопасности ClickOnce-приложений](https://docs.microsoft.com/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Другие элементы управления и возможности  
 В Windows Forms имеется множество других возможностей, которые упрощают и ускоряют реализацию общих задач, таких как создание диалоговых окон, печать, добавление справки и документации, а также локализация приложений на различных языках. Кроме того, Windows Forms применяется эффективная система безопасности [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], позволяя предоставить заказчикам более защищенные приложения.  
  
 Пошаговые инструкции по использованию этих функций см. в следующих разделах справки:  
  
|Целевой тип|См.|  
|--------|---------|  
|Печать содержимого формы|[Практическое руководство: печать графических изображений в формах Windows Forms](https://msdn.microsoft.com/library/741a0ktc.aspx)<br /><br /> [Практическое руководство: печать многостраничных текстовых файлов в Windows Forms](https://msdn.microsoft.com/library/cwbe712d.aspx)|   
|Дополнительные сведения о безопасности форм Windows Forms|[Безопасность в Windows Forms Overview](https://msdn.microsoft.com/library/90k49ccb.aspx)|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Общие сведения о Windows Forms](https://msdn.microsoft.com/library/8bxxy49h.aspx)   
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
