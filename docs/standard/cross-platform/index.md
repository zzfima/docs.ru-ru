---
title: "Разработка для нескольких платформ с помощью .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Разработка для нескольких платформ с помощью .NET Framework
Вы можете разрабатывать приложения для платформ Майкрософт и других поставщиков, используя .NET Framework и Visual Studio.  
  
## Варианты для межплатформенной разработки  
 Для разработки приложений для нескольких платформ можно использовать один исходный код или двоичные файлы, а также осуществлять вызовы между кодом .NET Framework и API\-интерфейсами среды выполнения Windows.  
  
|Цель...|Используйте...|  
|-------------|--------------------|  
|Совместное использование кода между приложениями Windows Phone 8.1 и Windows 8.1|**Общие проекты** \(шаблон универсальных приложений в Visual Studio 2013 с обновлением 2\).<br /><br /> -   В текущий момент Visual Basic не поддерживается.<br />-   Вы можете разделять код для определенных платформ с помощью операторов \#`if`.<br /><br /> Дополнительные сведения см. в следующих ресурсах:<br /><br /> -   [Создание приложений для Windows и Windows Phone с помощью Visual Studio](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) \(статья MSDN\)<br />-   [Использование Visual Studio для создания универсальных XAML\-приложений](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx) \(запись блога\)<br />-   [Использование Visual Studio для создания конвергированных XAML\-приложений](http://channel9.msdn.com/Events/Build/2014/3-591) \(видео\)|  
|Совместное использование двоичных файлов приложениями для различных платформ|**Проекты переносимой библиотеки классов** для кода, не зависящего от платформы.<br /><br /> -   Такой подход обычно используется для кода, который реализует бизнес\-логику.<br />-   Можно использовать Visual Basic или C\#.<br />-   Поддержка интерфейсов API зависит от платформы.<br />-   Проекты переносимой библиотеки классов для Windows 8.1 и Windows Phone 8.1 поддерживаются API среды выполнения Windows и XAML.  Эти функции недоступны в более старых версиях переносимой библиотеки классов.<br />-   При необходимости можно абстрагировать код для определенной платформы, используя интерфейсы или абстрактные классы.<br /><br /> Дополнительные сведения см. в следующих ресурсах:<br /><br /> -   [Переносная библиотека классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) \(статья MSDN\)<br />-   [Как заставить библиотеки переносимых классов работать на вас](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx) \(запись блога\)<br />-   [Использование переносимой библиотеки классов с MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md) \(статья MSDN\)<br />-   [Ресурсы приложений для библиотек, предназначенных для нескольких платформ](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md) \(статья MSDN\)<br />-   [Анализатор переносимости .NET](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) \(расширение Visual Studio\)|  
|Совместное использование кода между приложениями для платформ, отличных от Windows Phone 8.1 и Windows 8.1|Функция **Добавить как ссылку**.<br /><br /> -   Этот подход применим к логике, которая используется в обоих приложениях, но по каким\-либо причинам не может быть перенесена.  Эту функцию можно использовать в коде Visual Basic или C\#.<br />     Например, Windows Phone 8 и Windows 8 используют одни API среды выполнения Windows, но переносимые библиотеки классов не поддерживают среду выполнения Windows для этих платформ.  Вы можете использовать `Add as link` для совместного использования кода среды выполнения Windows между приложением Windows Phone 8 и приложением Магазина Windows, предназначенного для Windows 8.<br /><br /> Дополнительные сведения см. в следующих ресурсах:<br /><br /> -   [Совместное использование кода с помощью функции "Добавить как ссылку"](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx) \(статья MSDN\)<br />-   [Добавление существующих элементов в проект](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx) \(статья MSDN\)|  
|Создание приложений Магазина Windows с использованием .NET Framework или вызов API среды выполнения Windows из кода .NET Framework|Использование **API\-интерфейсов среды выполнения Windows** из кода .NET Framework на C\# или Visual Basic и использование .NET Framework для создания приложений Магазина Windows.  Следует помнить о различиях API двух платформ.  Однако существуют классы, помогающие обойти эти отличия.<br /><br /> Дополнительные сведения см. в следующих ресурсах:<br /><br /> -   [Поддержка приложений для Магазина Windows и среды выполнения Windows в .NET Framework](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) \(статья MSDN\)<br />-   [Передача URI в среду выполнения Windows](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) \(статья MSDN\)<br />-   <xref:System.IO.WindowsRuntimeStreamExtensions> \(страница справочника по API на портале MSDN\)<br />-   <xref:System.WindowsRuntimeSystemExtensions> \(страница справочника по API на портале MSDN\)|  
|Создание приложений .NET Framework для платформ других поставщиков|**Ссылочные сборки переносимой библиотеки классов** в .NET Framework и расширение Visual Studio или стороннее средство, например Xamarin.<br /><br /> Дополнительные сведения см. в следующих ресурсах:<br /><br /> -   [Переносимая библиотека классов теперь доступна на всех платформах.](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx) \(запись блога\)<br />-   [Xamarin](http://xamarin.com/visual-studio) \(веб\-сайт Xamarin\)|  
|Использование JavaScript и HTML для межплатформенной разработки|**Шаблоны универсальных приложений** в Visual Studio 2013 с обновлением 2 для разработки с использованием API среды выполнения Windows для платформ Windows 8.1 и Windows Phone 8.1.  В текущий момент нет возможности использовать JavaScript и HTML с API\-интерфейсами .NET Framework для разработки межплатформенных приложений.<br /><br /> Дополнительные сведения см. в следующих ресурсах:<br /><br /> -   [Шаблоны проектов JavaScript](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)<br />-   [Портирование приложения среды выполнения Windows с использованием JavaScript на платформу Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)|