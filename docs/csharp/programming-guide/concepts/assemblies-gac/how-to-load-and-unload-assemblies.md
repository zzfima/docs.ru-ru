---
title: Практическое руководство. Загрузка и выгрузка сборок (C#)
ms.date: 07/20/2015
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: 52f7173efe497ab286c607db681f256983adc077
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342048"
---
# <a name="how-to-load-and-unload-assemblies-c"></a>Практическое руководство. Загрузка и выгрузка сборок (C#)
Сборки, на которые ссылается программа, загружаются автоматически во время построения, но в текущий домен приложения можно также загрузить конкретные сборки во время выполнения. Дополнительные сведения см. в разделе [Как Загрузка сборок в домен приложения](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
 Отдельную сборку нельзя выгрузить, не выгрузив все домены приложений, в которых она содержится. Даже если сборка не входит в область, фактический файл сборки остается загруженным до тех пор, пока не будут выгружены домены приложений с этой сборкой.  
  
 Если необходимо выгрузить только часть сборок, создайте новый домен приложения, выполните код внутри этого домена, а затем выгрузите этот домен приложения. Дополнительные сведения см. в разделе [Как Выгрузка домена приложения](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>Загрузка сборки в домен приложения  
  
1. Используйте один из нескольких методов загрузки, содержащихся в классах <xref:System.AppDomain> и <xref:System.Reflection>. Дополнительные сведения см. в разделе [Как Загрузка сборок в домен приложения](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
### <a name="to-unload-an-application-domain"></a>Выгрузка домена приложения  
  
1. Отдельную сборку нельзя выгрузить, не выгрузив все домены приложений, в которых она содержится. Используйте метод `Unload` из <xref:System.AppDomain> для выгрузки доменов приложений. Дополнительные сведения см. в разделе [Как Выгрузка домена приложения](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)
- [Сборки в .NET](../../../../standard/assembly/index.md)
- [Практическое руководство. Загрузка сборок в домен приложения](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
