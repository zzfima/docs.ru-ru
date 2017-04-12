---
title: "Развертывание приложений, ссылающихся на компонент PrintForm (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 016643329d2ee66ca5a32f155cf91e0ee137f38f
ms.lasthandoff: 03/13/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>Развертывание приложений, ссылающихся на компонент PrintForm (Visual Basic)
Если требуется развернуть приложение, которое ссылается на <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента, компонент должен устанавливаться на конечном компьютере.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>Установка в качестве необходимого компонента PrintForm  
 Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение. Процесс установки необходимых компонентов называется *начальной загрузкой*.  
  
 Когда <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонент установлен на компьютере разработчика, пакет начального загрузчика Microsoft Visual Basic Power Packs добавляется [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] каталог загрузчика.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Этот пакет доступен, то при выполнении процедуры для добавления необходимых для [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] или развертывания установщика Windows.  
  
 По умолчанию компоненты начальной загрузки развертываются из расположения пакета установки. Кроме того, можно выбрать для развертывания этих компонентов URL-адрес или общую папку, откуда пользователь сможет скачать их при необходимости.  
  
> [!NOTE]
>  Чтобы установить компоненты начальной загрузки, пользователю могут потребоваться права администратора или аналогичные им на компьютере. Для [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] приложений, это означает, что пользователю могут потребоваться права администратора для установки приложения, независимо от уровня безопасности, заданного приложением. После установки приложения пользователь может запустить приложение без прав администратора.  
  
 Во время установки, пользователям будет предложено установить <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента, если он отсутствует на конечном компьютере.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 В качестве альтернативы начальному загрузчику можно предварительно развернуть <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>компонента с помощью электронной системы распространения как Microsoft Systems Management Server.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство: Установка необходимых компонентов с помощью приложения ClickOnce](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5)   
 [Компонент PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)
