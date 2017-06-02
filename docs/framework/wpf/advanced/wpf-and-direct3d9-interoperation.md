---
title: "Взаимодействие WPF и Direct3D9 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Direct3D9 [взаимодействие с WPF], создание содержимого Direct3D9"
  - "WPF, создание содержимого Direct3D9"
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Взаимодействие WPF и Direct3D9
Содержимое Direct3D9 можно включить в приложение Windows Presentation Foundation \(WPF\).  В этом разделе описывается, как создать содержимое Direct3D9, которое будет эффективно взаимодействовать с WPF.  
  
> [!NOTE]
>  При использовании содержимого Direct3D9 в WPF также нужно думать о производительности.  Дополнительные сведения об оптимизации производительности см. в разделе [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## Буферы отображения  
 Класс <xref:System.Windows.Interop.D3DImage> управляет двумя буферами отображения, которые называются *задним буфером* и *передним буфером*.  Задний буфер — это поверхность Direct3D9.  Изменения заднего буфера копируются в передний буфер при вызове метода <xref:System.Windows.Interop.D3DImage.Unlock%2A>.  
  
 На следующем рисунке показано отношение между задним и передним буфером.  
  
 ![Буферы отображения D3DImage](../../../../docs/framework/wpf/advanced/media/d3dimage-buffers.png "D3DImage\_buffers")  
  
## Создание устройства Direct3D9  
 Чтобы отобразить содержимое Direct3D9, необходимо создать устройство Direct3D9.  Имеются два объекта Direct3D9, которые можно использовать для создания устройства — `IDirect3D9` и `IDirect3D9Ex`.  Используйте эти объекты для создания устройств `IDirect3DDevice9` и `IDirect3DDevice9Ex` соответственно.  
  
 Создайте устройство вызовом одного из следующих методов.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 В Windows Vista или более поздней версии операционной системе, используйте метод `Direct3DCreate9Ex` с отображением который настроен для использования модели драйвера экрана Windows \(WDDM\).  Используйте метод `Direct3DCreate9` для любой другой платформы.  
  
### Доступность метода Direct3DCreate9Ex  
 D3d9.dll содержит метод `Direct3DCreate9Ex` только на Windows Vista или более поздней версии операционной системе.  При прямой ссылке на эту функцию в Windows XP приложение не удастся загрузить.  Чтобы определить, поддерживается ли метод `Direct3DCreate9Ex`, загрузите DLL и найдите адрес процедуры.  В следующем коде показано, как протестировать метод `Direct3DCreate9Ex`.  Полный пример кода см. в разделе [Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### Создание HWND  
 Для создания устройства требуется HWND.  В общем случае, можно создать вспомогательный HWND для использования Direct3D9.  В следующем примере кода показан способ создания вспомогательного объекта HWND.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### Представление параметров  
 Для создания устройства также требуется структура `D3DPRESENT_PARAMETERS`, но важны только несколько параметров.  Эти параметры выбраны для минимизации объема памяти.  
  
 Полям `BackBufferHeight` и `BackBufferWidth` присвойте значение 1.  При значении 0 потребуется задать размеры HWND.  
  
 Всегда устанавливайте флаги `D3DCREATE_MULTITHREADED` и `D3DCREATE_FPU_PRESERVE`, чтобы предупредить повреждение памяти, используемой Direct3D9, и защитить Direct3D9 от изменения параметров FPU.  
  
 В следующем коде показано, как инициализировать структуру `D3DPRESENT_PARAMETERS`.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## Создание заднего целевого буфера визуализации  
 Чтобы отобразить содержимое Direct3D9 в <xref:System.Windows.Interop.D3DImage>, создайте поверхность Direct3D9 и назначьте ее вызовом метода <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
### Проверка поддержки адаптера  
 Перед созданием поверхности проверьте, что все адаптеры поддерживают требуемые свойства поверхности.  Даже если прорисовка выполняется только в один адаптер, окно WPF может быть отображено на любом адаптере в системе.  Следует всегда писать код Direct3D9, обрабатывающий конфигурацию с несколькими адаптерами, а также проверять поддержку всех адаптеров, так как WPF может перемещать поверхность между доступными адаптерами.  
  
 В следующем примере кода показано, как проверить поддержку Direct3D9 всеми адаптерами в системе.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### Создание поверхности  
 Перед созданием поверхности проверьте, что возможности устройства поддерживают хорошую производительность в целевой операционной системе.  Дополнительные сведения см. в разделе [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 После проверки возможностей устройства можно создать поверхность.  В следующем примере кода показано, как создать целевой буфер визуализации.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### WDDM  
 В Windows Vista и более поздних операционных системах, настроитьы для использования WDDM, можно создать текстура однобуферной прорисовки и передачи уровнем 0 поверхностей методу <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  Этот способ не рекомендуется применять в Windows XP, так как нельзя создать блокируемую текстуру целевого буфера визуализации, и производительность будет снижена.  
  
## Обработка состояния устройства  
 Класс <xref:System.Windows.Interop.D3DImage> управляет двумя буферами отображения, которые называются *задним буфером* и *передним буфером*.  Задний буфер — это ваша поверхность Direct3D.  Изменения в заднему скопированные в буфер front кадровому буфер при вызове метода <xref:System.Windows.Interop.D3DImage.Unlock%2A>, где он отображается на оборудовании.  Иногда передний буфер становится недоступным.  Причинами этой недоступности могут быть блокировки экрана, приложения Direct3D, которые работают в полноэкранном монопольном режиме, переключение пользователей и другие системные события.  В этом случае приложение WPF уведомлено путем обработки события <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged>.  Например, приложение отвечает на зависит от кадрового буфера становить недоступным разрешено ли WPF для понизиться обратно в отрисовке программного обеспечения.  Метод <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> имеет перегрузку, которая принимает параметр, указывающий, содержится ли WPF в отрисовке программного обеспечения.  
  
 При вызове перегрузка <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> или вызовите перегруженный метод <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> с параметром `enableSoftwareFallback` установлен `false`, система отрисовки освобождает его ссылка на заднему буфер, если передний буфер становится недоступным и ничего не отображается.  Если передний буфер доступен, система отрисовки вызывает событие <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> для уведомления приложения WPF.  Можно создать обработчик событий для события <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> перезапуск визуализации заново с допустимыми поверхностью Direct3D.  Перезапуск отрисовка, необходимо вызвать <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 При вызове перегрузка <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> с параметром `enableSoftwareFallback` установлен `true`, система отрисовки сохраняет свою ссылку на заднему буфер, если передний буфер становится недоступным, поэтому нет необходимости вызывать <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> если передний буфер доступен еще раз.  
  
 Если отрисовка программного обеспечения включена, могут возникнуть ситуации, когда устройство пользователя становится недоступным, но система отрисовки сохраняет ссылку на поверхности Direct3D.  Для проверки недоступна, является ли устройство Direct3D9 вызовите метод `TestCooperativeLevel`.  Чтобы проверить устройства Direct3D9Ex вызовите метод `CheckDeviceState`, поскольку метод `TestCooperativeLevel` не рекомендуем и всегда возвращает успех.  Если устройство пользователя было недоступным, то вызов <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> чтобы освободить ссылку WPF в заднему буфер.  Если необходимо сбросить в устройство, вызовите <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> с параметром `backBuffer` установлен `null`, и затем вызовите <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> попытку с `backBuffer` install на допустимую Direct3D поверхность.  
  
 Вызовите метод `Reset`, чтобы вернуться из неработающего устройства, если реализована поддержка нескольких адаптеров.  Иначе освободите все интерфейсы Direct3D9 и полностью их пересоздайте.  Если разметка адаптера изменена, объекты Direct3D9, созданные до изменения, не обновляются.  
  
## Обработка изменения размера  
 Если <xref:System.Windows.Interop.D3DImage> отображается в разрешении за исключением его собственного размера, то его масштабирование в соответствии с текущим <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>, за исключением того, что <xref:System.Windows.Media.Effects.SamplingMode> заменяющее для <xref:System.Windows.Media.BitmapScalingMode>.  
  
 Если требуется более высокая точность, необходимо создать новую поверхность, когда изменяется размер контейнера с <xref:System.Windows.Interop.D3DImage>.  
  
 Имеется три способа обработки изменения размера.  
  
-   Обратитесь к системе макета и создайте новую поверхность, если изменяется размер.  Не создавайте слишком много поверхностей, так как можно израсходовать или фрагментировать память.  
  
-   Подождите, пока не будет создано событие изменения размера за фиксированный период времени, чтобы создать новую поверхность.  
  
-   Создайте <xref:System.Windows.Threading.DispatcherTimer>, который будет проверять размеры контейнера несколько раз в секунду.  
  
## Оптимизация нескольких мониторов  
 Значительное снижение производительности может произойти при перемещении <xref:System.Windows.Interop.D3DImage> системой отрисовки в другой монитор.  
  
 В WDDM пока мониторы работают на одной видео карте и используется `Direct3DCreate9Ex`, снижения производительности не происходит.  Производительность снижается, если мониторы используют разные видео карты.  В Windows XP производительность снижается всегда.  
  
 Если <xref:System.Windows.Interop.D3DImage> перемещается на другой монитор, чтобы восстановить хорошую производительность, можно создать новую поверхность на соответствующем адаптере.  
  
 Чтобы избежать снижения производительности, напишите отдельный код для каждого случая с применением нескольких мониторов.  В следующем списке показан один способ написания кода для нескольких мониторов.  
  
1.  Найдите точку объекта <xref:System.Windows.Interop.D3DImage> в пространстве экрана с помощью метода `Visual.ProjectToScreen`.  
  
2.  Используйте метод графического интерфейса `MonitorFromPoint`, чтобы найти монитор, отображающий эту точку.  
  
3.  Используйте метод `IDirect3D9::GetAdapterMonitor`, чтобы найти адаптер Direct3D9 этого монитора.  
  
4.  Если используется адаптер, отличный от адаптера заднего буфера, создайте новый задний буфер для нового монитора и назначьте его заднему буферу <xref:System.Windows.Interop.D3DImage>.  
  
> [!NOTE]
>  Если <xref:System.Windows.Interop.D3DImage> распределяется между несколькими мониторами, производительность будет снижена, за исключением использования WDDM и `IDirect3D9Ex` на одном адаптере.  В этой ситуации нет способа улучшить производительность.  
  
 В следующем примере кода показано, как найти текущий монитор.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Обновите монитор, если изменяется размер или позиция контейнера <xref:System.Windows.Interop.D3DImage>, или обновите монитор с помощью `DispatcherTimer`, который обновляется несколько раз в секунду.  
  
## Программная отрисовка WPF  
 WPF выполняет визуализацию синхронно для потока данных пользовательского интерфейса в следующих ситуациях.  
  
-   Печать  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 При возникновении одной из этих ситуаций система отрисовки вызывает метод <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A>, чтобы скопировать содержимое аппаратного буфера в программу.  Реализация по умолчанию вызывает метод `GetRenderTargetData` с пользовательской поверхностью.  Так как этот вызов происходит вне шаблона блокирования и разблокирования, он может завершиться ошибкой.  В этом случае, метод `CopyBackBuffer` возвращает значение `null`, и изображение не отображается.  
  
 Можно переопределить метод <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A>, вызвать базовую реализацию и, в случае возврата значения `null`, вернуть <xref:System.Windows.Media.Imaging.BitmapSource> местозаполнителя.  
  
 Также можно реализовать собственную программную отрисовку, вместо вызова базовой реализации.  
  
> [!NOTE]
>  Если WPF выполняет отрисовку полностью в программе, <xref:System.Windows.Interop.D3DImage> не отображается, так как WPF не имеет переднего буфера.  
  
## См. также  
 <xref:System.Windows.Interop.D3DImage>   
 [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)   
 [Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)   
 [Пошаговое руководство. Размещение содержимого Direct3D9 в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)