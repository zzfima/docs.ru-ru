---
title: "Кроссплатформенная разработка с переносной библиотекой классов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
caps.latest.revision: "95"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea0a111727093cb65a98e48255b06b3c4516d258
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2018
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Кроссплатформенная разработка с переносной библиотекой классов
Тип проекта "Переносимая библиотека классов .NET Framework" в Visual Studio позволяет быстро и легко создавать межплатформенные приложения и библиотеки для платформ Майкрософт.  
  
 Переносимые библиотеки классов уменьшают временные и трудовые затраты на разработку и тестирования кода. Используйте такой тип проекта для создания переносимых сборок .NET Framework, а затем ссылайтесь на них из приложений, предназначенных для различных платформ, таких как Windows и Windows Phone.  
  
 Даже после создания проекта переносимой библиотеки классов в Visual Studio и начала работы над проектом вы сможете изменить целевые платформы. Visual Studio скомпилирует вашу библиотеку с новыми сборками, что поможет определить, какие изменения следует внести в код.  
  
 В этой статье описывается разработка в Visual Studio, но корпорация Майкрософт также предоставляет ссылочные сборки переносимых библиотек классов, с помощью которые можно разрабатывать приложения и библиотеки в других средствах, таких как Xamarin. Их можно использовать в любой среде выполнения на основе .NET Framework даже на платформах других поставщиков. Дополнительные сведения об этих ссылочных сборках см. в записи блога [Переносимая библиотека классов (PCL) теперь доступна на всех платформах](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx). Для загрузки сборок, в разделе [ссылочные сборки Microsoft .NET переносимой библиотеки](http://www.microsoft.com/download/details.aspx?id=40727) в центре загрузки Майкрософт. Дополнительные сведения об использовании сборок в Xamarin см. в записи блога [PCL и библиотеки .NET NuGet теперь доступны для Xamarin](http://blogs.msdn.com/b/dotnet/archive/2013/11/13/pcl-and-net-nuget-libraries-are-now-enabled-for-xamarin.aspx).  
  
 Visual Studio предоставляет шаблоны, которые облегчают разработку с использованием переносимой библиотеки классов. В зависимости от используемой версии Visual Studio доступные шаблоны и меню могут отличаться от тех, что описаны в этой статье.  
  
> [!WARNING]
>  [Visual Studio 2013 с обновлением 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) включает обновления для шаблонов переносимой библиотеки классов. При наличии более ранней версии Visual Studio и Visual Studio 2013 установлен на том же компьютере, и вы установили обновление 2, чтобы изменения **требуемой версии .NET Framework** вариантов, которые будут применяться к обеим версиям Visual Studio.  
  
 В этом разделе.  
  
 [Поддержка Visual Studio](#vs_support)  
 [Создание проекта переносимой библиотеки классов](#create_pcl)  
 [Target-параметры](#platforms)  
 [Изменение целевой платформы](#change_targets)  
 [Поддерживаемые функции](#features)  
 [Поддерживаемые типы и члены](#members)  
 [Отличия API в переносимой библиотеки классов](#API_diff)  
 [Использование переносимой библиотеки классов](#using)  
  
<a name="vs_support"></a>   
## <a name="visual-studio-support"></a>Поддержка Visual Studio  
 Поддержка переносимой библиотеки классов в Visual Studio зависит от используемой версии Visual Studio. В некоторых случаях у вас будут все необходимые компоненты, а в других случаях потребуется установить дополнительные компоненты, как показано в следующей таблице.  
  
|Visual Studio SKU|Поддержка создания переносимой библиотеки классов|  
|-----------------------|---------------------------------------------------|  
|Visual Studio 2010 Professional, Premium или Ultimate|Да, при установке [Portable Library Tools](https://marketplace.visualstudio.com/items?itemName=BCLTeam.PortableLibraryTools2).|  
|Версии Visual Studio Express 2010|Нет.|  
|Visual Studio 2012 Professional, Premium или Ultimate|Да. Техническая поддержка по телефону, установите [Windows Phone SDK 8.0](http://go.microsoft.com/fwlink/?LinkId=265772).|  
|Версии Visual Studio Express 2012|Нет.|  
|Visual Studio 2013 Professional, Premium или Ultimate|Да. Поддержка Windows Phone 8.1 установите [Visual Studio 2013 с обновлением 2](http://go.microsoft.com/fwlink/p/?LinkId=393658).|  
|Visual Studio Express 2013 для Windows|Да, при установке [последнюю версию Visual Studio Express](http://go.microsoft.com/fwlink/p/?LinkId=394629), которой включающая обновление 2, или добавьте [Visual Studio 2013 с обновлением 2](http://go.microsoft.com/fwlink/p/?LinkId=393658).|  
  
<a name="create_pcl"></a>   
## <a name="creating-a-portable-class-library-project"></a>Создание проекта переносимой библиотеки классов  
 Для создания переносимой библиотеки классов следует использовать один из шаблонов в Visual Studio. Создайте новый проект и в **новый проект** диалогового **шаблоны**, выберите целевой язык (C# или Visual Basic) и выберите одну из платформ, вы будете работать. Другие платформы можно выбрать на следующем шаге.  
  
 В Visual Studio 2013 с обновлением 2 вы можете **библиотека классов (переносимая)** шаблона для выбранного языка и платформы, чтобы создать переносимую библиотеку классов. Этот шаблон отображается для следующих платформ:  
  
-   Приложения Магазина  
  
-   Настольный компьютер Windows  
  
-   Silverlight  
  
 Если вы хотите создать библиотеку, предназначенные для Windows Phone 8.1 и Windows 8.1 на языке C#, вы можете **приложения магазина**, а затем выберите **библиотека классов (переносимая для универсальных приложений)**.  
  
 ![Переносимая библиотека классов для приложений магазина](../../../docs/standard/cross-platform/media/storeuniversalpcl.png "StoreUniversalPCL")  
  
 При использовании этого шаблона Windows 8.1 и Windows Phone 8.1 автоматически выбираются как целевые платформы. Если создать библиотеку только для Windows Phone 8.1 или Windows 8.1, вы сможете изменить и добавить целевые платформы позднее.  
  
 Если вы используете Visual Studio 2012 или Visual Studio 2013 без обновления 2, создайте новый проект и выберите **переносимой библиотеки классов** шаблон в Visual C# или Visual Basic.  
  
 ![Выбор проекта переносимой библиотеки](../../../docs/standard/cross-platform/media/portablelibrary-start.png "PortableLibrary_start")  
  
 **Добавление переносимой библиотеки классов** откроется диалоговое окно, и можно выбрать дополнительные платформы. В зависимости от выбранных платформ могут отображаться предупреждения о совместимости.  
  
 ![Изменение целевой платформы и диалоговое окно для VS2013](../../../docs/standard/cross-platform/media/clr-pcl-changeframeworks.png "CLR_PCL_ChangeFrameworks")  
Диалоговое окно добавления переносимой библиотеки классов для Visual Studio 2013 с обновлением 2  
  
 Независимо от того, используете ли вы Visual Studio 2012 или Visual Studio 2013, вы можете выбрать платформы при создании проекта переносимой библиотеки классов или изменить целевые платформы в свойствах проекта после его создания.  
  
<a name="platforms"></a>   
## <a name="target-options"></a>Доступные целевые платформы  
 При создании проекта переносимой библиотеки классов можно выбрать операционную систему и целевую версию .NET Framework. Если вы используете Visual Studio 2013 и установили обновление 2 или более поздней версии, вы можете **библиотека классов (переносимая для универсальных приложений)** шаблона для создания переносимой библиотеки классов, предназначенного для Windows 8.1 и Windows Phone 8.1. В следующей таблице показаны доступные целевые платформы, зависящие от используемой версии Visual Studio.  
  
|Целевая платформа|Visual Studio 2012|Visual Studio 2013|Visual Studio 2013 с обновлением 2 или более поздняя версия|  
|-|-|-|-|  
|.NET Framework|-.NET framework 4 и более поздних версий<br /><br /> -.NET framework 4.0.3 и более поздние версии<br /><br /> -.NET framework 4.5|-.NET framework 4 и более поздних версий<br /><br /> -.NET framework 4.0.3 и более поздние версии<br /><br /> -.NET framework 4.5 и более поздних версий<br /><br /> -.NET framework 4.5.1|-.NET framework 4<br /><br /> -.NET framework 4.0.3<br /><br /> -.NET framework 4.5<br /><br /> -.NET framework 4.5.1|  
|Windows Phone|-Windows Phone 7 и более поздних версий<br /><br /> -Windows Phone 7.5 и более поздних версий<br /><br /> -Windows Phone 8|-Windows Phone 8|-Windows Phone Silverlight 8<br /><br /> -Windows Phone Silverlight 8.1<br /><br /> Для поддержки среды выполнения Windows и XAML выберите:<br /><br /> -Windows Phone 8.1|  
|Магазин Windows|-.NET приложений для магазина Windows|— Приложения для магазина Windows (Windows 8) и более поздних версий<br /><br /> -Для магазина Windows (Windows 8.1)|— Windows 8<br /><br /> — Windows 8.1|  
|-Silverlight|-Silverlight 4 и более поздних версий<br /><br /> -Silverlight 5|-Silverlight 5|-Silverlight 5|  
|Xbox|-Xbox 360|Н/Д|Н/Д|  
  
<a name="change_targets"></a>   
## <a name="changing-targets"></a>Изменение целевой платформы  
 После выбора шаблона переносимой библиотеки классов платформы по умолчанию выбираются автоматически, но они зависят от установленной версии Visual Studio и ранее выбираемых платформ. Вы можете изменить платформы при создании переносимой библиотеки классов или после начала разработки библиотеки.  
  
 Если вы хотите изменить целевые платформы после создания проекта, в **обозревателе решений**, откройте контекстное меню для проекта переносимой библиотеки классов (не решения) и нажмите кнопку **свойства** . На странице свойств проекта **библиотеки** вкладке указаны платформы сейчас направлен проект.  
  
 ![Свойства проекта](../../../docs/standard/cross-platform/media/portablelibrary-projectproperties.png "PortableLibrary_ProjectProperties")  
Страница свойств переносимой библиотеки классов для Visual Studio 2013 с обновлением 2  
  
 Чтобы добавить или удалить целевые объекты, выберите **изменений** кнопки и затем установите или снимите соответствующие флажки.  
  
 При изменении целевых платформ API-интерфейсы, доступные для разработки проекта, изменятся в соответствии с выбранными платформами. Visual Studio отображает ошибки и предупреждения после изменения целевых платформ.  
  
 Если вы хотите оценить переносимость сборки до можно внести изменения в Visual Studio, можно использовать [анализатор переносимости .NET](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).  
  
 Пункты меню зависят от используемой версии Visual Studio.  
  
 ![Изменение целевой версии](../../../docs/standard/cross-platform/media/portablelibrary.png "PortableLibrary_")  
Диалоговое окно изменения целевых платформ в Visual Studio 2012  
  
<a name="features"></a>   
## <a name="supported-features"></a>Поддерживаемые функции  
 В следующей таблице показано, какие функции поддерживаются различными платформами и версиями. В некоторых случаях корпорация Майкрософт добавила поддержку пакета NuGet, это обозначено в уведомлении. Дополнительные сведения о пакетах NuGet для платформы .NET Framework см. в разделе [.NET Framework и выпуски по каналу](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md).  
  
|Функция|.NET Framework|.NET Framework|.NET Framework|Магазин Windows|Магазин Windows|Магазин Windows Phone|Windows Phone Silverlight|Windows Phone Silverlight|Windows Phone Silverlight|Silverlight|Silverlight|Xbox 360|  
|-------------|--------------------|--------------------|--------------------|-------------------|-------------------|-------------------------|-------------------------------|-------------------------------|-------------------------------|-----------------|-----------------|--------------|  
||**4**|**4.0.3**|**4.5**|**8**|**8.1**|**8.1**|**7.5**|**8**|**8.1**|**4**|**5**||  
|Основные библиотеки|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|  
|Поддержка асинхронного выполнения|➊|➊|✓|✓|✓|✓|➊|➊|✓|➊|➊||  
|Сжатие|||✓|✓|✓|✓||➋|➋||||  
|Заметки к данным||✓|✓|✓|✓|||||✓|✓||  
|Ключевое слово dynamic|✓|✓|✓|✓|✓|||||✓|✓||  
|HTTPClient|➌|➌|✓|✓|✓|✓|➌|➌|➌|➌|➌||  
|IQueryable|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓||  
|LINQ|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓||  
|Managed Extensibility Network (MEF)|✓|✓|✓|✓|✓|||||✓|✓||  
|Сетевая библиотека классов (NCL)|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓||  
|Сериализация (контракт данных, XML и JSON)|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓||  
|System.Numerics|✓|✓|✓|✓|✓|||||✓|✓||  
|Модели представлений (MVVM)|||✓|✓|✓|✓|✓|✓|✓|✓|✓||  
|Windows Communication Foundation (WCF)|✓|✓|✓|✓|✓||✓|✓|✓|✓|✓||  
|API среды выполнения Windows|||||✓|✓|||||||  
|Windows.UI.XAML|||||✓|✓|||||||  
|XLINQ||✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓|  
  
 ➊ Требуется [Microsoft Async](https://www.nuget.org/packages/Microsoft.Bcl.Async/) пакета  
 ➋ Требуется [Microsoft Compression](https://www.nuget.org/packages/Microsoft.Bcl.Compression) пакета  
 ➌ Требуется [клиентских библиотек HTTP Майкрософт](http://www.nuget.org/packages/Microsoft.Net.Http) пакета  
  
> [!WARNING]
>  Могут возникнуть ошибки при ссылке на [Microsoft Compression](https://www.nuget.org/packages/Microsoft.Bcl.Compression) и [клиентских библиотек HTTP Майкрософт](http://www.nuget.org/packages/Microsoft.Net.Http) пакетов из переносимой библиотеки, используемой приложением Windows Phone Silverlight 8.1. Дополнительные сведения см. в разделе [совместимость платформ и критические изменения для приложений Windows Phone Silverlight 8.1](http://go.microsoft.com/fwlink/p/?LinkId=394744).  
  
<a name="members"></a>   
## <a name="supported-types-and-members"></a>Поддерживаемые типы и члены  
 Типы и члены, доступные в проектах переносимой библиотеки классов, ограничены несколькими факторами совместимости:  
  
-   они должны быть общими для выбранных целевых платформ;  
  
-   они должны вести себя аналогичным образом на всех этих платформах;  
  
-   они не должны быть кандидатами на вывод из употребления;  
  
-   они должны иметь смысл в переносимой среде, особенно если вспомогательные члены не являются переносимыми.  
  
 Например, переносимая библиотека классов содержит типы, связанные с пользовательским интерфейсом, только если в качестве целевых платформ выбраны Windows 8.1 и Windows Phone 8.1. Кроме того, столкнуться с ограничениями также можно при нацеливании на платформы (такие как Xbox, .NET Framework 4 и Windows Phone 7), выпущенные до выхода переносимой библиотеки классов. Через NuGet выпускаются пакеты .NET Framework, которые улучшает поддержку переносимой библиотеки классов для некоторых из более старых платформ. Дополнительные сведения и список пакетов NuGet см. в разделе [.NET Framework и выпуски по каналу](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md).  
  
 Если член поддерживается в переносимой библиотеке классов и для выбранных целевых платформ, он будет показан в IntelliSense в вашем проекте. Кроме того, значок переносимой библиотеки классов ![поддерживается переносимой библиотекой](../../../docs/standard/cross-platform/media/portablelibrary-referenceicon.png "PortableLibrary_ReferenceIcon") появится в таблицах членов в [библиотекиклассов.NETFramework](https://msdn.microsoft.com/library/mt472912.aspx) рядом с поддерживаемыми членами. Например, в следующей таблице показано, что свойство <xref:System.String.Chars%2A> класса <xref:System.String> поддерживается в переносимой библиотеке классов:  
  
 ![Значок поддерживаемого члена](../../../docs/standard/cross-platform/media/plibsupportedmemberlist.png "PlibSupportedMemberList")  
Значок переносимой библиотеки классов  
  
 Можно также обратиться к **сведения о версии** раздела справки о для примечанием, что тип или член поддерживается проекта переносимой библиотеки классов:  
  
 ![Сведения о версии переносимой библиотеки](../../../docs/standard/cross-platform/media/plibversioninformation.png "PlibVersionInformation")  
Пример сведений о версии  
  
 Однако помните, что интерфейс API может поддерживаться в переносимой библиотеки классов, но возможность его использования зависит от выбранных целевых платформ.  
  
<a name="API_diff"></a>   
## <a name="api-differences-in-the-portable-class-library"></a>Отличия API в переносимой библиотеке классов  
 Для обеспечения совместимости сборок переносимой библиотеки классов на всех поддерживаемых платформах некоторые члены в переносимой библиотеке классов были немного изменены.  
  
<a name="using"></a>   
## <a name="using-the-portable-class-library"></a>Использование переносимой библиотеки классов  
 После построения проекта переносимой библиотеки классов просто добавьте ссылку на нее в других проектах. Можно сделать ссылку на проект или на конкретные сборки, содержащие классы, к которым требуется доступ.  
  
 Для запуска приложения, ссылающегося на сборку переносимой библиотеки классов, на компьютере должны быть установлены требуемые (или более поздние) версии целевых платформ. Visual Studio содержит все необходимые платформы, поэтому приложение можно запустить без дальнейших изменений на компьютере, который использовался для его разработки.  
  
### <a name="deploying-a-windows-store-or-windows-phone-app"></a>Развертывание приложения Магазина Windows или Windows Phone  
 При создании приложения Магазина Windows или Windows Phone, которое ссылается на сборку переносимой библиотеки классов, все необходимые компоненты для развертывания приложения уже включены в пакет приложения, другие действия не требуются.  
  
### <a name="deploying-a-net-framework-app"></a>Развертывание приложения .NET Framework  
 При развертывании приложения .NET Framework, в котором имеется ссылка на сборку переносимой библиотеки классов, необходимо задать зависимость от нужной версии платформы .NET Framework. Задание этой зависимости обеспечивает установку нужной версии вместе с приложением. Если целевой платформы .NET Framework 4 или более поздней версии, на компьютере должен быть .NET Framework 4 с [обновление](http://go.microsoft.com/fwlink/?LinkId=210824), обновлением 4.0.3 для .NET Framework 4 или .NET Framework 4.5.  
  
-   Чтобы создать зависимость с развертыванием ClickOnce: В **обозревателе решений**, выберите узел проекта для проекта, необходимо опубликовать. (Это проект, в котором имеется ссылка на проект переносимой библиотеки классов.) В строке меню выберите **проекта**, **свойства**и нажмите кнопку **публикации** вкладки. На **публикации** выберите **необходимых компонентов**. Отметьте требуемую версию платформы .NET Framework (или обновление платформы .NET Framework 4) как необходимый компонент.  
  
-   Чтобы создать зависимость с проектом установки: В **обозревателе решений**, выберите проект установки. В строке меню выберите **проекта**, **свойства**, **необходимых компонентов**. Отметьте требуемую версию платформы .NET Framework как необходимый компонент.  
  
 Дополнительные сведения о развертывании приложений .NET Framework см. в разделе [руководство по развертыванию для разработчиков](../../../docs/framework/deployment/deployment-guide-for-developers.md).  
  
### <a name="deploying-a-silverlight-based-app"></a>Развертывание приложения Silverlight  
 При развертывании приложения Silverlight, ссылающегося на сборку переносимой библиотеки классов, необходимо убедиться, что минимальная версия среды выполнения, требуемая приложению, соответствует его целевой версии. В случае Silverlight 4 версия должна быть 4.0.60129.0 или более поздняя. Версия указывается путем включения параметра `<param name="minRuntimeVersion" value="4.0.60129.0" />` в веб-страницу, на которой размещено приложение Silverlight, следующим образом:  
  
```xaml  
<div id="silverlightControlHost">  
    <object data="data:application/x-silverlight-2,"   
           type="application/x-silverlight-2" width="100%" height="100%">  
    <param name="source" value="ClientBin/SilverlightApplication.xap"/>  
    <param name="onError" value="onSilverlightError" />  
    <param name="background" value="white" />  
    <param name="minRuntimeVersion" value="4.0.60129.0" />  
    <param name="autoUpgrade" value="true" />  
    <a href="http://go.microsoft.com/fwlink/?LinkID=149156&v=4.0.50826.0"   
             style="text-decoration:none">  
      <img src=http://go.microsoft.com/fwlink/?LinkId=161376  
             alt="Get Microsoft Silverlight" style="border-style:none"/>  
    </a>  
  </object>  
   <iframe id="_sl_historyFrame"   
              style="visibility:hidden;height:0px;width:0px;border:0px">  
   </iframe>  
</div>  
```  
  
## <a name="see-also"></a>См. также  
 [Использование переносимой библиотеки классов с MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)  
 [Ресурсы приложений для библиотек, предназначенных для нескольких платформ](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)  
 [Анализатор переносимости .NET](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)  
 [Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
 [Развертывание](../../../docs/framework/deployment/net-framework-applications.md)
