---
title: "Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings - объект, создание сетки свойств для параметров пользователя"
  - "сетки свойств"
  - "сетки свойств, создание для параметров пользователя"
  - "параметры пользователей, создание сеток свойств"
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Можно создать сетку свойств для параметров пользователя, заполнив элемент управления <xref:System.Windows.Forms.PropertyGrid> свойствами параметров пользователей объекта `My.Settings`.  
  
> [!NOTE]
>  Для работы данного примера необходимо настроить параметры пользователей приложения.  Дополнительные сведения см. в разделе [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
 Объект `My.Settings` представляет каждый параметр в виде свойства.  Имя свойства совпадает с именем параметра, а тип свойства совпадает с типом параметра.  Параметр **Область** определяет, доступно ли свойство только для чтения; если область задана как **Приложение**, то свойство доступно только для чтения, а если область задана как **Пользователь**, то свойство доступно для чтения и записи.  Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Изменить или сохранить значения параметров области определения приложения во время выполнения невозможно.  Эти параметры можно изменить только при создании приложения \(с помощью **Конструктора проектов**\) или путем изменения файла конфигурации приложения.  Дополнительные сведения см. в разделе [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
 В этом примере используется элемент управления <xref:System.Windows.Forms.PropertyGrid> для доступа к свойствам параметров пользователей объекта `My.Settings`.  По умолчанию в элементе управления <xref:System.Windows.Forms.PropertyGrid> отображаются все свойства объекта `My.Settings`.  Однако свойства параметров пользователей имеют атрибут <xref:System.Configuration.UserScopedSettingAttribute>.  В этом примере свойству <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> <xref:System.Windows.Forms.PropertyGrid> присваивается значение <xref:System.Configuration.UserScopedSettingAttribute>, чтобы отображались только свойства параметров пользователей.  
  
### Добавление сетки свойств параметров пользователей  
  
1.  Добавьте элемент управления **PropertyGrid** из **панели элементов** на поверхность проектирования приложения — в данном случае предполагается, что это `Form1`.  
  
     По умолчанию элементу управления сетки свойств присваивается имя `PropertyGrid1`.  
  
2.  Дважды щелкните поверхность проектирования для `Form1`, чтобы открыть код обработчика событий загрузки формы.  
  
3.  Задайте объект `My.Settings` в качестве выделенного объекта для сетки свойств.  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  Настройте сетку свойств для отображения только параметров пользователей.  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  Чтобы отображать только параметры области определения приложения, используйте атрибут <xref:System.Configuration.ApplicationScopedSettingAttribute> вместо <xref:System.Configuration.UserScopedSettingAttribute>.  
  
## Отказоустойчивость  
 Приложение сохраняет параметры пользователя при завершении работы приложения.  Чтобы сохранить параметры немедленно, вызовите метод `My.Settings.Save`.  Дополнительные сведения см. в разделе [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## См. также  
 [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Практическое руководство. Чтение параметров приложения в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)