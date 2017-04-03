---
title: "Практическое руководство. Загрузка и выгрузка сборок (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 15905b2c23320b57e5797d6084ce48cfc526ed7d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a>Практическое руководство. Загрузка и выгрузка сборок (C#)
Сборки, на которые ссылается программа, загружаются автоматически во время построения, но в текущий домен приложения можно также загрузить конкретные сборки во время выполнения. Дополнительные сведения см. в разделе [Практическое руководство. Загрузка сборок в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
 Отдельную сборку нельзя выгрузить, не выгрузив все домены приложений, в которых она содержится. Даже если сборка не входит в область, фактический файл сборки остается загруженным до тех пор, пока не будут выгружены домены приложений с этой сборкой.  
  
 Если необходимо выгрузить только часть сборок, создайте новый домен приложения, выполните код внутри этого домена, а затем выгрузите этот домен приложения. Дополнительные сведения см. в разделе [Практическое руководство. Выгрузка домена приложения](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>Загрузка сборки в домен приложения  
  
1.  Используйте один из нескольких методов загрузки, содержащихся в классах <xref:System.AppDomain> и <xref:System.Reflection>. Дополнительные сведения см. в разделе [Практическое руководство. Загрузка сборок в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
### <a name="to-unload-an-application-domain"></a>Выгрузка домена приложения  
  
1.  Отдельную сборку нельзя выгрузить, не выгрузив все домены приложений, в которых она содержится. Используйте метод `Unload` из <xref:System.AppDomain> для выгрузки доменов приложений. Дополнительные сведения см. в разделе [Практическое руководство. Выгрузка домена приложения](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)   
 [Сборки и глобальный кэш сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [Практическое руководство. Загрузка сборок в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)
