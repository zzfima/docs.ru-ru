---
title: "Практическое руководство. Создание дочерних MDI-форм | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "дочерние формы"
  - "MDI - интерфейс, создание форм"
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Практическое руководство. Создание дочерних MDI-форм
Дочерние формы MDI являются основным элементом [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), так как они находятся в центре взаимодействия с пользователями.  
  
 С помощью описанной ниже процедуры создаются дочерние формы MDI, отображающие элемент управления <xref:System.Windows.Forms.RichTextBox> аналогично большинству текстовых приложений.  Замена элемента управления <xref:System.Windows.Forms> на другие элементы управления, такие как <xref:System.Windows.Forms.DataGridView>, или на сочетание элементов управления позволяет создавать дочерние окна MDI \(а также приложения MDI\) с различными возможностями.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.  Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Создание дочерних форм MDI  
  
1.  Создайте проект Windows Forms.  В окне **Свойства** формы присвойте свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`, а свойству `WindowsState` — значение `Maximized`.  
  
     При этом форма назначается в качестве MDI\-контейнера для дочерних окон.  
  
2.  Из `Toolbox` перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> в форму.  Присвойте свойству `Text` значение **File**.  
  
3.  Нажмите кнопку с многоточием \(…\) рядом со свойством **Items** и выберите пункт **Добавить**, чтобы добавить два дочерних элемента типа "меню панели инструментов".  Присвойте свойству `Text` этих элементов значения **Создать** и **Окно**.  
  
4.  В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите команду **Добавить**, а затем **Добавить новый элемент**.  
  
5.  В диалоговом окне **Добавление нового элемента** на панели **Шаблоны** выберите **Форма Windows Forms** \(в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) или **Приложение Windows Forms \(.NET\)** \(в [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\).  В поле **Имя** введите имя формы Form2.  Нажмите кнопку **Открыть**, чтобы добавить форму в проект.  
  
    > [!NOTE]
    >  Дочерняя форма MDI, созданная на этом этапе, является стандартной формой Windows Forms.  Таким образом, у нее есть свойство <xref:System.Windows.Forms.Form.Opacity%2A>, которое позволяет управлять прозрачностью формы.  Однако свойство <xref:System.Windows.Forms.Form.Opacity%2A> предназначено для окон верхнего уровня.  Его не следует использовать в дочерних формах MDI, иначе могут возникнуть проблемы с рисованием.  
  
     Эта форма будет шаблоном для дочерних форм MDI.  
  
     Откроется **конструктор Windows Forms** с формой Form2.  
  
6.  Из **панели элементов** перетащите на форму элемент управления **RichTextBox**.  
  
7.  В окне **Свойства** задайте для свойства `Anchor` значение **Top, Left**, а для свойства `Dock` — значение **Fill**.  
  
     В результате элемент управления <xref:System.Windows.Forms.RichTextBox> будет целиком заполнять область дочерней формы MDI, даже если ее размеры изменятся.  
  
8.  Дважды щелкните пункт меню **Создать**, чтобы создать для него обработчик событий <xref:System.Windows.Forms.Control.Click>.  
  
9. Вставьте код, аналогичный приведенному ниже, чтобы при выборе пользователем пункта меню **Создать** создавалась дочерняя форма MDI.  
  
    > [!NOTE]
    >  В примере ниже обработчик событий обрабатывает событие <xref:System.Windows.Forms.Control.Click> для `MenuItem2`.  Имейте в виду, что в зависимости от особенностей архитектуры приложения пункт меню **Создать** может не являться `MenuItem2`.  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     При использовании [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] добавьте следующую директиву `#include` в начало формы Form1.h:  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. В раскрывающемся списке в верхней части окна **Свойства** выберите пункт меню, соответствующий пункту **Файл**, и задайте для свойства <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> значение <xref:System.Windows.Forms.ToolStripMenuItem> пункта "Окно".  
  
     Благодаря этому в меню **Окно** будет приводиться список открытых дочерних окон MDI с флажком рядом с активным окном.  
  
11. Нажмите клавишу F5 для запуска приложения.  Выбирая команду **Создать** в меню **Файл**, можно создавать дочерние формы MDI, которые отслеживаются в меню **Окно**.  
  
    > [!NOTE]
    >  Когда в дочерней форме MDI есть компонент <xref:System.Windows.Forms.MainMenu> \(обычно обладающий структурой пунктов меню\) и он открыт внутри родительской формы MDI, также имеющей компонент <xref:System.Windows.Forms.MainMenu> \(обычно обладающий структурой пунктов меню\), пункты меню будут объединены автоматически, если задано свойство <xref:System.Windows.Forms.MenuItem.MergeType%2A> \(и, возможно, свойство <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>\).  Установите для свойства <xref:System.Windows.Forms.MenuItem.MergeType%2A> обоих компонентов <xref:System.Windows.Forms.MainMenu> и всех пунктов меню дочерней формы значение <xref:System.Windows.Forms.MenuMerge>.  Кроме того, установите свойство <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> таким образом, чтобы пункты обоих меню приводились в нужном порядке.  Необходимо помнить, что при закрытии родительской формы MDI каждая из дочерних форм MDI создает событие <xref:System.Windows.Forms.Form.Closing> до создания события <xref:System.Windows.Forms.Form.Closing> для родительской формы MDI.  Отмена события <xref:System.Windows.Forms.Form.Closing> дочерней формы MDI не отменяет событие <xref:System.Windows.Forms.Form.Closing> родительской формы MDI. Однако для аргумента <xref:System.ComponentModel.CancelEventArgs> для события <xref:System.Windows.Forms.Form.Closing> родительской формы MDI будет установлено значение `true`.  Чтобы принудительно закрыть родительскую и все дочерние формы MDI, задайте для аргумента <xref:System.ComponentModel.CancelEventArgs> значение `false`.  
  
## См. также  
 [Приложения с интерфейсом MDI](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Практическое руководство. Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Практическое руководство. Определение активной дочерней MDI\-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [Практическое руководство. Отправка данных в активную дочернюю MDI\-форму](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)