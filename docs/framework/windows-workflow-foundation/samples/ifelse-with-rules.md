---
title: "Действие IfElse с правилами"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5cd0859db8071f9af130756fdc9b34726199be9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ifelse-with-rules"></a>Действие IfElse с правилами
В данном образце демонстрируется использование условий правила для действия класса <xref:System.Workflow.Activities.IfElseActivity>.  
  
 В данном образце из узла передается параметр `OrderValue`. Значение параметра используется в условии правила для первого ответвления действия класса <xref:System.Workflow.Activities.IfElseActivity>. Если значение меньше 10 000, выполняет первую ветвь и <xref:System.Workflow.Activities.CodeActivity> действия в первом ответвлении выводит **получение руководителя** на консоль. Если значение больше 10 000, <xref:System.Workflow.Activities.CodeActivity> действия во втором разветвлении выполняется и выводится **получить утверждение вице-Президент**.  
  
### <a name="to-build-the-sample"></a>Сборка образца  
  
1.  Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.  
  
3.  Запустите решение без отладки, нажав сочетание клавиш CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Выполнение образца  
  
-   В окне командной строки пакета SDK запустите файл с расширением EXE в папке «IfElseWithRules\bin\debug» (или в папке «IfElseWithRules\bin» для образца в Visual Basic), вложенной в главную папку образца.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец находится в следующем каталоге:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
