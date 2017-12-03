---
title: "Действия с регулярными выражениями"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77968872d878f7b4d6b0eb3f27516a75abb54919
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="regular-expression-activities"></a>Действия с регулярными выражениями
Этот образец демонстрирует способ создания набора действий, которые представляют функциональные возможности регулярного выражения пространства имен <xref:System.Text.RegularExpressions>. Такие пользовательские действия можно использовать в приложении рабочего процесса. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]в разделе Регулярные выражения [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) пространства имен.  
  
 В следующей таблице приведены сведения о пользовательских действиях, выполняемых в данном образце.  
  
|Действие|Описание|  
|--------------|-----------------|  
|IsMatch|Указывает, были ли найдены совпадения во входной строке в результате выполнения регулярного выражения.|  
|Соответствия|Выполняет поиск всех вхождений регулярного выражения во входной строке и возвращает все найденные совпадения.|  
|Заменить|Заменяет в указанной входной строке все строки, совпадающие с шаблоном регулярного выражения, на указанную строку замены.|  
  
## <a name="ismatch"></a>IsMatch  
 Пользовательское действие `IsMatch` возвращает `true`, если свойство строки `Input` совпадает с регулярным выражением, указанным в свойстве `Pattern`. Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>.  
  
 В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `IsMatch`.  
  
|Свойство или возвращаемое значение|Описание|  
|------------------------------|-----------------|  
|Шаблон (обязательно)|Регулярное выражение, по которому выполняется поиск.|  
|Входные данные (обязательно)|Входная строка для поиска.|  
|RegexOptions|Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.|  
|Возвращаемое значение|`true`, если входная строка совпадает с указанным шаблоном. В противном случае `false`.|  
  
 В следующем примере кода показано использование настраиваемого действия `IsMatch`.  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a>Соответствия  
 Пользовательское действие `Matches` выполняет поиск всех вхождений регулярного выражения во входной строке и возвращает все найденные совпадения. Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.Matches%2A>.  
  
 В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `IsMatch`.  
  
|Свойство или возвращаемое значение|Описание|  
|------------------------------|-----------------|  
|Шаблон (обязательно)|Регулярное выражение, по которому выполняется поиск.|  
|Входные данные (обязательно)|Входная строка для поиска.|  
|RegexOptions|Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.|  
|Возвращаемое значение|Объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий коллекцию успешных совпадений.|  
  
 В следующем примере кода показано использование настраиваемого действия `Matches`.  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a>Заменить  
 Пользовательское действие `Replace` выполняет поиск во входной строке и заменяет в этой строке все строки, совпадающие с указанным регулярным выражением. Действие является производным от <xref:System.Activities.CodeActivity%601>, и в методе <xref:System.Activities.CodeActivity%601.Execute%2A> вызывается метод <xref:System.Text.RegularExpressions.Regex.Replace%2A>.  
  
 В следующей таблице описываются свойства и возвращаемое значение для настраиваемого действия `Replace`.  
  
|Свойство или возвращаемое значение|Описание|  
|------------------------------|-----------------|  
|Шаблон (обязательно)|Регулярное выражение, по которому выполняется поиск.|  
|Входные данные (обязательно)|Входная строка для поиска.|  
|Замена|Строка замены.<br /><br /> Если задано свойство `Replacement`, то свойство `MatchEvaluator` не учитывается. Необходимо задать либо свойство `Replacement`, либо свойство `MatchEvaluator`.|  
|MatchEvaluator|Пользовательский метод, анализирующий каждое совпадение и возвращающий либо исходную строку с совпадениями, либо строку замены.<br /><br /> Если задано свойство `Replacement`, то свойство `MatchEvaluator` не учитывается. Необходимо задать либо свойство `Replacement`, либо свойство `MatchEvaluator`.|  
|RegexOptions|Побитовое сочетание OR [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) значений перечисления.|  
|Возвращаемое значение|Объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий коллекцию успешных совпадений.|  
  
 В следующем примере кода показано использование настраиваемого действия `Replace`.  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения RegexActivities.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`