---
title: "Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице | Microsoft Docs"
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
  - "кэширование [платформа .NET Framework], позиции дочерней таблицы"
  - "позиции дочерней таблицы"
  - "выделение строк дочерних таблиц"
  - "текущая позиция дочерней таблицы"
  - "привязка данных [платформа .NET Framework], выделение строк"
  - "представление "основной-подробности" [Windows Forms]"
  - "представление "основной-подробности""
  - "родительский/дочерний - представление [Windows Forms]"
  - "сброс позиции дочерней таблицы"
  - "позиция строки [Windows Forms]"
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице
Зачастую при работе с привязкой данных в формах Windows Forms, данные будут отображаться в виде представлений «родительский\-дочерний» или «основной\-подробности».  Это относится к сценариям привязки данных, где отображаются данные из одного источника в двух элементах управления.  Изменение выделения в одном элементе управления вызывает изменение данных, отображаемых во втором элементе управления.  Например, первый элемент управления может содержать список клиентов, а второй — список заказов, связанных с выбранным клиентом из первого элемента управления.  
  
 Начиная с .NET Framework версии 2.0, при отображении данных в представлении «родительский\-дочерний» может потребоваться предпринять дополнительные действия, чтобы убедиться в том, что выбранная строка в дочерней таблице не сбрасывается на первую строку таблицы.  Для этого необходимо кэшировать позицию дочерней таблицы и сбрасывать ее после изменения родительской таблицы.  Обычно сброс дочерних таблиц происходит после первого изменения поля в строке родительской таблицы.  
  
### Кэширование текущей позиции дочерней таблицы  
  
1.  Объявите целочисленную переменную для хранения позиции в дочернем списке и логическую переменную для хранения признака, следует ли кэшировать позицию дочерней таблицы.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2.  Обработайте событие <xref:System.Windows.Forms.CurrencyManager.ListChanged> для привязки <xref:System.Windows.Forms.CurrencyManager> и проверьте значение <xref:System.ComponentModel.ListChangedType> из <xref:System.ComponentModel.ListChangedType>.  
  
3.  Проверьте текущую позицию <xref:System.Windows.Forms.CurrencyManager>.  Если она больше, чем первая запись в списке \(обычно 0\), сохраните ее в переменной.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4.  Обработайте событие <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> родительского списка для родительского диспетчера денежного формата.  В обработчике задайте логическое значение, указывающее, что он не относится к сценарию кэширования.  Если возникает <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>, то в родительском объекте происходит изменение, которое  является изменением позиции в списке, а не изменением значения элемента.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### Сброс позиции дочерней таблицы  
  
1.  Обработайте событие <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> для дочерней привязки<xref:System.Windows.Forms.CurrencyManager>.  
  
2.  Установите позицию в дочерней таблице на кэшированную позицию, сохраненную в предыдущей процедуре.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## Пример  
 В следующем примере показано, как сохранить текущую позицию в <xref:System.Windows.Forms.CurrencyManager> для дочерней таблицы и сбросить позицию после завершения изменения родительской таблицы.  Этот пример содержит два элемента управления <xref:System.Windows.Forms.DataGridView>, которые привязаны к двум таблицам в <xref:System.Data.DataSet> с помощью компонента <xref:System.Windows.Forms.BindingSource>.  Между двумя таблицами установлено отношение, добавлено отношение к <xref:System.Data.DataSet>.  В демонстрационных целях позиция дочерней таблицы изначально установлена на третью строку.  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 Чтобы проверить пример кода, выполните следующие действия.  
  
1.  Запустите пример.  
  
2.  Убедитесь, что флажок **Кэшировать и сбрасывать позицию** установлен.  
  
3.  Нажмите кнопку **Очистить родительское поле**, чтобы произвести изменение поля родительской таблицы.  Обратите внимание, что выбранная строка в дочерней таблице не изменяется.  
  
4.  Закройте и снова запустите пример.  Это необходимо сделать, поскольку сброс происходит только при первом изменении в родительской строке.  
  
5.  Убедитесь, что флажок **Кэшировать и сбрасывать позицию** установлен.  
  
6.  Нажмите кнопку **Очистить родительское поле**.  Обратите внимание, что выбранная строка в дочерней таблице становится первой строкой.  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing, System.Windows.Forms и System.XML.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 [Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)   
 [Компонент BindingSource](../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Связывание данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)