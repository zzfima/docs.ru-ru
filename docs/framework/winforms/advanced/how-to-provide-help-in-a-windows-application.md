---
title: "Руководство: предоставление справки в приложении Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d23e5d5d19e17aedd37d4d5f6cbc41429463ddfb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-provide-help-in-a-windows-application"></a>Руководство: предоставление справки в приложении Windows
Можно использовать из <xref:System.Windows.Forms.HelpProvider> компонента для присоединения разделов справки в файле справки для определенных элементов управления в формах Windows Forms. Файл справки может быть в формате HTML, HTMLHelp 1.x или следующих версий.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-provide-help"></a>Предоставление справки  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.HelpProvider> форму компонента.  
  
     Компонент разместится в нижней части конструктора Windows Forms.  
  
2.  В **свойства** задайте <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> свойство на файл справки .chm, .col или htm.  
  
3.  Выберите другой элемент управления на форму, а в **свойства** задайте <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> свойство.  
  
     Это строка, передаваемая через <xref:System.Windows.Forms.HelpProvider> в файле справки для вызова соответствующего раздела справки.  
  
4.  В **свойства** задайте <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> свойство в значение <xref:System.Windows.Forms.HelpNavigator> перечисления.  
  
     Этот параметр определяет способ, которым свойство **HelpKeyword** передается в справочную систему. В следующей таблице показаны возможные настройки и их описания.  
  
    |Имя элемента|Описание:|  
    |-----------------|-----------------|  
    |AssociateIndex|Указывает, что индекс для данного раздела выполняется в заданном URL-адресе.|  
    |Find|Указывает, что отображается страница поиска заданного URL-адреса.|  
    |Индекс|Указывает, что отображается индекс заданного URL-адреса.|  
    |KeywordIndex|Указывает ключевое слово для поиска и действие, выполняемое по указанному URL-адресу.|  
    |TableOfContents|Указывает, что отображается оглавление файла справки HTML 1.0.|  
    |Раздел|Указывает, что отображается раздел, на который ссылается указанный URL-адрес.|  
  
 Во время выполнения, нажав клавишу F1 при элемента управления, для которого заданы **HelpKeyword** и **HelpNavigator** свойства — имеет фокус откроется файл справки, связанный с этим <xref:System.Windows.Forms.HelpProvider> компонента.  
  
 В настоящее время свойство **HelpNamespace** поддерживает файлы справки в следующих трех форматах: HTMLHelp 1.x, HTMLHelp 2.0 и HTML. Таким образом, для свойства **HelpNamespace** можно задать адрес http://, например веб-страницу. Если это будет сделано, откроется браузер по умолчанию для веб-страницы со строкой, указанной в свойстве **HelpKeyword**, которая используется в качестве привязки. Привязка используется для перехода к определенной части HTML-страницы.  
  
> [!IMPORTANT]
>  Обязательно проверьте все сведения, отправляемые с клиента, перед их использованием в приложении. Злоумышленники могут попытаться послать или вставить исполняемый сценарий, инструкции SQL или другой код. Перед отображением ввода пользователя, сохранением его в базе данных или работой с ним убедитесь, что он не содержит потенциально небезопасных сведений. Например, можно порекомендовать использование регулярного выражения для поиска ключевых слов, таких как SCRIPT, при получении данных от пользователя.  
  
 Можно также использовать <xref:System.Windows.Forms.HelpProvider> компонент для отображения всплывающей справки, даже если он настроен на отображение файлов справки для элементов управления Windows Forms. Дополнительные сведения см. в разделе [Практическое руководство. Отображение всплывающей справки](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Отображение всплывающей справки](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [Отображение справки по элементам управления с помощью подсказок](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Интеграция справки пользователя в формы Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
