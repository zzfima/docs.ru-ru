---
title: "Практическое руководство. Использование свойств Modifiers и GenerateMember"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcb79525e557a66ed471bc38dcbdd444d75ba6b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>Практическое руководство. Использование свойств Modifiers и GenerateMember
При размещении компонента в форме Windows Forms, два свойства предоставляются средой разработки: `GenerateMember` и `Modifiers`. `GenerateMember` Свойство указывает, когда конструктор Windows Forms создает переменную-член для компонента. `Modifiers` Свойство имеет модификатор доступа, назначенный этой переменной-члена. Если значение `GenerateMember` свойство `false`, значение `Modifiers` свойство не имеет значения.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a>Чтобы указать, является ли компонент элементом формы  
  
1.  В конструкторе Windows Forms откройте форму.  
  
2.  Откройте **элементов**и поместите в форме три <xref:System.Windows.Forms.Button> элементов управления.  
  
3.  Задать `GenerateMember` и `Modifiers` свойства для каждого <xref:System.Windows.Forms.Button> управления согласно следующей таблице.  
  
    |Имя кнопки|Значение GenerateMember|Значение модификаторов|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|Без изменений|  
  
4.  Постройте решение.  
  
5.  В **обозревателе решений** нажмите кнопку **Показать все файлы**.  
  
6.  Откройте **Form1** узел и в **редактор кода**откройте **Form1.Designer.vb** или **Form1.Designer.cs** файла. Этот файл содержит код, созданный конструктором Windows Forms.  
  
7.  Найдите объявления для трех кнопок. В следующем примере кода показаны различия, указанные `GenerateMember` и `Modifiers` свойства.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  По умолчанию, конструктор Windows Forms присваивает `private` (`Friend` в Visual Basic) модификатор контейнерных элементов управления, таких как <xref:System.Windows.Forms.Panel>. Если с основным <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Form> имеет контейнерный элемент управления не будет принимать новые дочерние элементы в наследуемых элементов управления и форм. Рекомендуется изменить модификатор элемента управления базового контейнера для `protected` или `public`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Button>  
 [Визуальное наследование в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [Пошаговое руководство. Демонстрация визуального наследования](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [Практическое руководство. Наследование форм Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)
