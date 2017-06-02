---
title: "Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms | Microsoft Docs"
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
  - "ElementHost - элемент управления, копирование и вставка во время разработки"
  - "взаимодействие [WPF]"
  - "Windows Forms, копирование и вставка содержимого"
  - "пользовательский элемент управления WPF, размещение в Windows Forms"
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms
В этом пошаговом руководстве описывается, как скопировать элемент управления Windows Presentation Foundation \(WPF\) из одной формы Windows Forms в другую.  
  
 В руководстве выполняются следующие задачи:  
  
-   создание проекта;  
  
-   копирование элемента управления WPF.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.  Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Создание проекта  
 Для начала следует создать проект Windows Forms.  
  
> [!NOTE]
>  При размещении содержимого WPF поддерживаются только проекты C\# и Visual Basic.  
  
#### Создание проекта  
  
-   Создайте проект приложения Windows Forms в Visual Basic или Visual C\# с именем `CopyElementHost`.  
  
## Копирование элемента управления WPF  
 После добавления в проект элемента управления WPF его можно скопировать в другие формы проекта.  
  
#### Копирование элемента управления WPF  
  
1.  Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.  Используйте имя по умолчанию для этого типа элемента управления \(`UserControl1.xaml`\).  Подробнее см. в разделе [Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Выполните построение проекта.  
  
3.  Откройте `Form1` в конструкторе Windows Forms.  
  
4.  Перетащите экземпляр `UserControl1` из **панели элементов** на форму.  
  
     Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.  
  
5.  Выбрав элемент управления `elementHost1`, нажмите клавиши CTRL\+C, чтобы скопировать его в буфер обмена.  
  
6.  Добавьте в проект новую форму Windows Forms.  Используйте имя по умолчанию для этого типа формы \(`Form2`\).  
  
7.  При открытой в конструкторе Windows Forms форме `Form2` нажмите клавиши CRTL\+V, чтобы вставить в форму копию `elementHost1`.  
  
     Скопированный элемент управления также имеет имя `elementHost1`, так как это закрытое поле класса `Form2`.  Конфликта имен с `elementHost1` в классе `Form1` не возникает.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Использование элементов управления WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)