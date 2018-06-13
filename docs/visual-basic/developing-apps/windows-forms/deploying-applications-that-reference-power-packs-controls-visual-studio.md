---
title: Развертывание приложений, ссылающихся на элементы управления пакетов Power Packs (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
ms.openlocfilehash: bd235bc0b4a7f9978333931ae1dce012c0950374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587509"
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Развертывание приложений, ссылающихся на элементы управления пакетов Power Packs (Visual Studio)
Если вы хотите развернуть приложение, которое ссылается на элементы управления пакетов Power Packs (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, или <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), элементы управления необходимо установить на конечном компьютере.  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Установка элементов управления пакетов Power Packs как необходимый компонент  
 Для успешного развертывания приложения необходимо также развернуть все компоненты, на которые ссылается приложение. Процесс установки необходимых компонентов называется *начальной загрузкой*.  
  
 При установке Visual Studio на компьютере разработчика, пакет начального загрузчика Power Packs добавляется в папку начального загрузчика Visual Studio. Этот пакет доступен при добавлении необходимых компонентов для [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] или для развертывания установщика Windows.  
  
 По умолчанию компоненты начальной загрузки развертываются из расположения пакета установки. Кроме того, можно выбрать для развертывания этих компонентов URL-адрес или общую папку, откуда пользователь сможет скачать их при необходимости.  
  
> [!NOTE]
>  Чтобы установить компоненты начальной загрузки, пользователю могут потребоваться права администратора или аналогичные им на компьютере. Для приложений [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] это означает, что пользователю могут потребоваться права администратора для установки приложения независимо от уровня безопасности, заданного приложением. После установки приложения пользователь может запустить приложение без прав администратора.  
  
 Во время установки пользователям будет предложено установить элементы управления пакетов Power Packs, если они не присутствуют на конечном компьютере.  
  
 В качестве альтернативы начальному загрузчику можно предварительно развернуть элементы управления пакетов Power Packs с помощью электронной системы распространения по как Microsoft Systems Management Server.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Установка необходимых компонентов для приложения ClickOnce](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [Элементы управления Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
