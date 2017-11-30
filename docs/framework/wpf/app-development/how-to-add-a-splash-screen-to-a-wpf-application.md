---
title: "Практическое руководство. Добавление в WPF-приложение экрана-заставки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 973f35f6bfa259490a9423bf0b69d676ad968372
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Практическое руководство. Добавление в WPF-приложение экрана-заставки
В этом разделе показано, как добавить окно запуска, или *экран-заставка*, приложение Windows Presentation Foundation (WPF).  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a>Чтобы добавить существующее изображение в качестве экрана-заставки  
  
1.  Создать или найти изображение, которое будет использоваться для экрана-заставки. Можно использовать любой формат образа, который поддерживается в Windows компонент обработки Изображений. Например можно использовать формат BMP, GIF, JPEG, PNG и TIFF.  
  
2.  Добавьте файл изображения в проект приложения WPF. Дополнительные сведения см. в разделе [NIB: Практическое: Добавление существующих элементов в проект](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
3.  В обозревателе решений выберите изображение.  
  
4.  В окне «Свойства» щелкните стрелку раскрывающегося списка для **действие при построении** свойство.  
  
5.  Выберите **экран-заставка** из раскрывающегося списка.  
  
    > [!NOTE]
    >  Если вы не видите **экран-заставка** , то проверьте, что вы используете [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] с пакетом обновления 1 или более поздней версии.  
  
6.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
     Изображение экрана-заставки отображается в центре экрана и исчезнет при появлении главного окна приложения.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>Для удаления экрана-заставки из приложения  
  
1.  В обозревателе решений выберите изображение экрана-заставки.  
  
2.  В окне свойств задайте **действие при построении** для **нет**.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>Для удаления экрана-заставки из приложения  
  
-   В обозревателе решений удалите изображение экрана-заставки.  
  
-   Изображение экрана-заставки исключите из проекта.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.SplashScreen>  
 [NIB: Практическое: Добавление существующих элементов в проект](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
