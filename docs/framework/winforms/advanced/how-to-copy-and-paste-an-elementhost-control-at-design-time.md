---
title: "Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки | Microsoft Docs"
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
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки
В этой процедуре показано, как скопировать элемент управления WPF в форму Windows Forms.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Копирование и вставка элемента управления ElementHost во время режима разработки.  
  
1.  Добавьте новый элемент управления WPF <xref:System.Windows.Controls.UserControl> в проект Windows Forms.  Используйте имя по умолчанию \(`UserControl1.xaml`\) для данного типа элемента управления.  Дополнительные сведения см. в разделе [Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  В окне **Свойства** присвойте свойствам <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> элемента управления `UserControl1` значение `200`.  
  
3.  Присвойте свойству <xref:System.Windows.Controls.Control.Background%2A> значение `Blue`.  
  
4.  Выполните построение проекта.  
  
5.  Откройте форму `Form1` в конструкторе Windows Forms.  
  
6.  Перетащите элемент управления `UserControl1` из **панели элементов** в форму.  
  
     Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.  
  
7.  При выбранном элементе управления `elementHost1` нажмите клавиши CTRL\+C для копирования его в буфер обмена.  
  
8.  Нажмите клавиши CTRL\+V для вставки скопированного элемента управления в форму.  
  
     Новый элемент управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost2` будет создан в форме.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)   
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Использование элементов управления WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)