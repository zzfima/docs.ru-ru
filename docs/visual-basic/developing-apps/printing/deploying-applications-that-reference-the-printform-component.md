---
title: Развертывание приложений, ссылающихся на компонент PrintForm (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
ms.openlocfilehash: 6384ad6e3bf0520362267eddc8f7bbb05b37f283
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400430"
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>Развертывание приложений, ссылающихся на компонент PrintForm (Visual Basic)
Если требуется развернуть приложение, которое ссылается на компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> , этот компонент должен быть установлен на целевом компьютере.  
  
 Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать [центра загрузки](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>Установка PrintForm в качестве необходимого компонента  
 Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение. Процесс установки необходимых компонентов называется *начальной загрузкой*.  
  
 Когда <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> на компьютере разработки установлен компонент, пакет начального загрузчика Microsoft Visual Basic Power Packs добавляется в каталог начального загрузчика Visual Studio. Этот пакет доступен при добавлении необходимых компонентов для [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] или для развертывания установщика Windows.  
  
 По умолчанию компоненты начальной загрузки развертываются из расположения пакета установки. Кроме того, можно выбрать для развертывания этих компонентов URL-адрес или общую папку, откуда пользователь сможет скачать их при необходимости.  
  
> [!NOTE]
>  Чтобы установить компоненты начальной загрузки, пользователю могут потребоваться права администратора или аналогичные им на компьютере. Для приложений [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] это означает, что пользователю могут потребоваться права администратора для установки приложения независимо от уровня безопасности, заданного приложением. После установки приложения пользователь может запустить приложение без прав администратора.  
  
 Во время установки пользователям будет предложено установить компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> , если он отсутствует на целевом компьютере.  
  
 В качестве альтернативы начальному загрузчику можно предварительно развернуть компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> с помощью электронной системы распространения ПО, например Microsoft Systems Management Server.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Установка необходимых компонентов для приложения ClickOnce](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [Компонент PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)
