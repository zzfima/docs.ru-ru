---
title: "Практическое руководство. Использование свойств Modifiers и GenerateMember | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Designer_GenerateMember"
  - "Designer_Modifiers"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "базовые формы"
  - "наследование форм"
  - "GenerateMember - свойство"
  - "наследование, формы"
  - "наследуемые формы"
  - "наследуемые формы, Windows Forms"
  - "Modifiers - свойство"
  - "Windows Forms, наследование"
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Использование свойств Modifiers и GenerateMember
При размещении компонента в форме Windows Forms два свойства предоставляются средой разработки: `GenerateMember` и `Modifiers`.  Свойство `GenerateMember` указывает, когда конструктор Windows Forms создает переменную\-элемент для компонента.  Свойство `Modifiers` — это модификатор доступа, назначенный этой переменной\-элементу.  Если значение свойства `GenerateMember` равно `false`, значение свойства `Modifiers` не действует.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы указать, является ли компонент элементом формы, выполните следующие действия.  
  
1.  В конструкторе Windows Forms откройте форму.  
  
2.  Перетащите три элемента управления <xref:System.Windows.Forms.Button> из **панели элементов** в форму.  
  
3.  Установите свойства `GenerateMember` и `Modifiers` для каждого элемента управления <xref:System.Windows.Forms.Button> в соответствии со следующей таблицей.  
  
    |Имя кнопки|Значение GenerateMember|Значение модификатора|  
    |----------------|-----------------------------|---------------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|Без изменений|  
  
4.  Выполните построение решения.  
  
5.  В **обозревателе решений** нажмите кнопку **Показать все файлы**.  
  
6.  Откройте узел **Form1** и в **редакторе кода** откройте **Form1.Designer.vb** или **Form1.Designer.cs**.  Этот файл содержит код, созданный конструктором Windows Forms.  
  
7.  Найдите объявления для этих трех кнопок.  В следующем примере программы показаны различия, указанные свойствами `GenerateMember` и `Modifiers`.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  По умолчанию конструктор Windows Forms назначает модификатор `private` \(`Friend` в Visual Basic\) контейнерным элементам управления, таким как <xref:System.Windows.Forms.Panel>.  Если базовый элемент управления <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Form> имеет контейнер, он не примет новые дочерние элементы в унаследованных элементах управления и формах.  Для решения этой проблемы следует изменить модификатор базового контейнера на `protected` или `public`.  
  
## См. также  
 <xref:System.Windows.Forms.Button>   
 [Визуальное наследование в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)   
 [Пошаговое руководство. Демонстрация визуального наследования](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)   
 [Практическое руководство. Наследование форм Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)