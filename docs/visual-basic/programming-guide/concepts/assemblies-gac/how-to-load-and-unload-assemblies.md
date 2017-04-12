---
title: "Практическое руководство: загрузка и выгрузка сборок (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 460d3a18fdee74c9b9c49ee465247b5b12d554d8
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>Практическое руководство: загрузка и выгрузка сборок (Visual Basic)
Сборки ссылается программа будет автоматически загружаться во время построения, но можно также загрузить конкретные сборки в текущий домен приложения во время выполнения. Дополнительные сведения см. в разделе [Практическое руководство: загрузка сборки в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
 Там будет невозможно выгружать отдельные сборки без выгрузки всех доменов приложений, которые его содержат. Даже если сборка выходит за пределы области, фактический файл сборки будет оставаться загруженными, пока не будут выгружены все домены приложений, которые его содержат.  
  
 Если вы хотите выгрузить только некоторые сборки, рассмотрите возможность создания нового домена приложения, выполните код внутри этого домена и затем выгрузите это домен приложения. Дополнительные сведения см. в разделе [как: выгрузка домена приложения](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>Для загрузки сборки в домен приложения  
  
1.  Используйте один из нескольких методов загрузки, содержащихся в классы <xref:System.AppDomain>и <xref:System.Reflection>.</xref:System.Reflection> </xref:System.AppDomain> Дополнительные сведения см. в разделе [Практическое руководство: загрузка сборки в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
### <a name="to-unload-an-application-domain"></a>Чтобы выгрузить домен приложения  
  
1.  Там будет невозможно выгружать отдельные сборки без выгрузки всех доменов приложений, которые его содержат. Используйте `Unload` метод <xref:System.AppDomain>для выгрузки доменов приложений.</xref:System.AppDomain> Дополнительные сведения см. в разделе [как: выгрузка домена приложения](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Практическое руководство: загрузка сборок в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)
