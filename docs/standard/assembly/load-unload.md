---
title: Руководство. Загрузка и выгрузка сборок
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: a520ffd41c3465737be7494d374cbcf64e3f1b85
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155780"
---
# <a name="how-to-load-and-unload-assemblies"></a>Руководство. Загрузка и выгрузка сборок
Сборки, на которые ссылается программа, загружаются автоматически средой CLR, но в текущий домен приложения можно также динамически загрузить конкретные сборки. Дополнительные сведения см. в разделе [Как Загрузка сборок в домен приложения](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).

В .NET Framework отдельную сборку невозможно выгрузить, не выгрузив все домены приложений, в которых она содержится. Даже если сборка не входит в область, фактический файл сборки остается загруженным до тех пор, пока не будут выгружены домены приложений с этой сборкой. В .NET Core класс <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> обрабатывает выгрузку сборок. Дополнительные сведения см. в разделе [Использование и отладка сборок с возможностью выгрузки в .NET Core](unloadability.md).

## <a name="load-and-unload-assemblies"></a>Загрузка и выгрузка сборок

Для загрузки сборки в домен приложения используйте один из нескольких методов загрузки, содержащихся в классах <xref:System.AppDomain> и <xref:System.Reflection.Assembly>. Дополнительные сведения см. в разделе [Как Загрузка сборок в домен приложения](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md). Обратите внимание, что .NET Core поддерживает только один домен приложения.

Чтобы выгрузить сборку в .NET Framework, нужно выгрузить все домены приложений, содержащие ее. Чтобы выгрузить домен приложения, используйте метод <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Как Выгрузка домена приложения](../../framework/app-domains/how-to-unload-an-application-domain.md).

Если нужно выгрузить только часть сборок в приложении .NET Framework, создайте новый домен приложения, выполните код внутри этого домена, а затем выгрузите этот домен приложения. Дополнительные сведения см. в разделе [Как Выгрузка домена приложения](../../framework/app-domains/how-to-unload-an-application-domain.md).  

## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../../csharp/programming-guide/index.md)
- [Основные понятия программирования (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Сборки в .NET](index.md)
- [Руководство. Загрузка сборок в домен приложения](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
