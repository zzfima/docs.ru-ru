---
title: "Взаимодействие WPF и Direct3D9"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1bd4d7486f546a340a4c722d140c6c7f5cee707
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="wpf-and-direct3d9-interoperation"></a>Взаимодействие WPF и Direct3D9
Содержимое Direct3D9 можно включить в приложении Windows Presentation Foundation (WPF). В этом разделе описывается создание содержимого Direct3D9, чтобы эффективно взаимодействовать с WPF.  
  
> [!NOTE]
>  При использовании содержимого Direct3D9 в WPF, необходимо также подумать о производительности. Дополнительные сведения об оптимизации производительности см. в разделе [вопросы производительности Direct3D9 и взаимодействие с WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
## <a name="display-buffers"></a>Буферы отображения  
 <xref:System.Windows.Interop.D3DImage> Класс управляет двумя буферами отображения, которые называются *заднего буфера* и *кадровый буфер*. Задний буфер — это поверхность Direct3D9. Изменения заднего буфера копируются вперед в передний буфер при вызове <xref:System.Windows.Interop.D3DImage.Unlock%2A> метода.  
  
 На следующем рисунке показана связь между заднего буфера и кадровый буфер.  
  
 ![Буферы отображения D3DImage](../../../../docs/framework/wpf/advanced/media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Создания устройства Direct3D9  
 Чтобы отобразить содержимое Direct3D9, необходимо создать устройство Direct3D9. Имеется два объекта Direct3D9, которые можно использовать для создания устройства, `IDirect3D9` и `IDirect3D9Ex`. Эти объекты можно использовать для создания `IDirect3DDevice9` и `IDirect3DDevice9Ex` устройств, соответственно.  
  
 Создание устройства путем вызова одного из следующих методов.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 В Windows Vista или более поздней версии операционной системы, используйте `Direct3DCreate9Ex` метод с отображением, настроенный на использование модели драйвер WDDM. Используйте `Direct3DCreate9` метод на любую другую платформу.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>Доступность метода Direct3DCreate9Ex  
 Имеет d3d9.dll `Direct3DCreate9Ex` метод только в Windows Vista или более поздней версии операционной системы. При прямой ссылке на эту функцию в Windows XP, приложение не удастся загрузить. Чтобы определить, является ли `Direct3DCreate9Ex` метод поддерживается, загрузить библиотеку DLL и найдите адрес процедуры. Ниже показано, как для проверки `Direct3DCreate9Ex` метод. Полный пример кода см. в разделе [Пошаговое руководство: создание Direct3D9 содержимого для размещения в WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>Создание HWND  
 Для создания устройства требуется HWND. Как правило создается вспомогательный HWND для использования Direct3D9. В следующем примере кода показано, как создать вспомогательный HWND.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>Представление параметров  
 Для создания устройства также требуется `D3DPRESENT_PARAMETERS` важны структуры, но только несколько параметров. Эти параметры выбраны для минимизации объема памяти.  
  
 Задать `BackBufferHeight` и `BackBufferWidth` поля значение 1. Значение 0 приводит к их присваивается размеры HWND.  
  
 Всегда значение `D3DCREATE_MULTITHREADED` и `D3DCREATE_FPU_PRESERVE` флаги, чтобы предотвратить повреждение памяти, используемой Direct3D9 и защитить Direct3D9 от изменения параметров FPU.  
  
 Следующий код демонстрирует способ инициализации `D3DPRESENT_PARAMETERS` структуры.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>Создание целевого объекта отрисовки заднего буфера  
 Чтобы отобразить содержимое Direct3D9 в <xref:System.Windows.Interop.D3DImage>, создайте поверхность Direct3D9 и назначьте его путем вызова <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> метод.  
  
### <a name="verifying-adapter-support"></a>Проверка поддержки адаптера  
 Перед созданием поверхности, проверьте, что все адаптеры поддерживают поверхности свойства, которые вам необходимы. Даже если прорисовка выполняется только один адаптер, окно WPF может отображаться на одном адаптере в системе. Следует всегда писать код Direct3D9, обрабатывающий конфигурацию с несколькими адаптерами и следует проверять все адаптеры для поддержки, так как WPF может перемещать поверхность между доступными адаптерами.  
  
 В следующем примере кода показано, как проверить, поддерживают все адаптеры для Direct3D9 в системе.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>Создание рабочей области  
 Перед созданием поверхности, убедитесь, что возможности устройства поддерживают хорошую производительность в целевой операционной системы. Дополнительные сведения см. в разделе [вопросы производительности Direct3D9 и взаимодействие с WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
 После проверки возможности устройства, можно создать области. В следующем примере кода показано, как создать целевой объект отрисовки.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 В Windows Vista и более поздних операционных системах, которые настроены для использования WDDM, можно создать текстуру целевого отрисовки и область уровня 0, чтобы передать <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> метод. Такой подход не рекомендуется в ОС Windows XP, поскольку не удается создать текстуру целевого блокируемый отрисовки и производительность будет снижена.  
  
## <a name="handling-device-state"></a>Обработка состояния устройства  
 <xref:System.Windows.Interop.D3DImage> Класс управляет двумя буферами отображения, которые называются *заднего буфера* и *кадровый буфер*. Задний буфер — это ваша поверхность Direct3D.  Изменения заднего буфера копируются вперед в передний буфер при вызове <xref:System.Windows.Interop.D3DImage.Unlock%2A> метода, где он отображается на оборудовании. В некоторых случаях кадровый буфер становится недоступной. Отсутствие доступности может быть вызвано блокировки экрана, полноэкранном режиме монопольного приложения Direct3D, переключение пользователей или другие системные события. В этом случае приложение WPF уведомляется, обрабатывая <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> событий.  Как приложение реагирует на кадровый буфер становится недоступным, зависит от того, включен ли переход к программной отрисовки WPF. <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> Имеет перегрузку, которая принимает параметр, указывает ли WPF возвращается к программной отрисовки.  
  
 При вызове <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> перегружать или вызвать <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> перегрузка с `enableSoftwareFallback` равным `false`, система отрисовки освобождает свою ссылку на задний буфер, когда кадровый буфер становится недоступной, и ничего не отображается. Когда кадровый буфер снова станет доступной, система отрисовки вызывает <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> событие для уведомления приложения WPF.  Можно создать обработчик событий для <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> событий перезапуск подготовки к просмотру с допустимым поверхность Direct3D. Чтобы перезапустить подготовки отчетов, необходимо вызвать метод <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>.  
  
 При вызове <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> перегрузка с `enableSoftwareFallback` равным `true`, система отрисовки сохраняет свою ссылку на задний буфер кадровый буфер становится недоступной, поэтому нет необходимости вызывать <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> при вперед буфер доступен еще раз.  
  
 При включении программной отрисовки, могут возникнуть ситуации, его устройство становится недоступной, когда система отрисовки сохраняет ссылку на поверхность Direct3D. Чтобы проверить, является ли устройство Direct3D9 недоступен, вызовите `TestCooperativeLevel` метод. Для проверки вызова устройств Direct3D9Ex `CheckDeviceState` метода, так как `TestCooperativeLevel` метод является устаревшим и всегда завершается успешно. Если устройство пользователя стала недоступной, вызовите <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> для освобождения WPF ссылку на заднего буфера.  Если необходимо выполнить сброс устройства, вызовите <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> с `backBuffer` равным `null`и затем вызвать <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> с `backBuffer` присвоено допустимое поверхность Direct3D.  
  
 Вызовите `Reset` способ устранения неработающего устройства только в том случае, если реализована поддержка нескольких адаптеров. В противном случае Освободите все интерфейсы Direct3D9 и создайте их повторно полностью. Если разметка адаптера изменена, объекты Direct3D9, созданные до изменения не обновляются.  
  
## <a name="handling-resizing"></a>Обработка изменения размера  
 Если <xref:System.Windows.Interop.D3DImage> отображается с разрешением, отличный от исходного размера, он масштабируется в соответствии с текущим <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>, за исключением того, что <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> заменяется <xref:System.Windows.Media.BitmapScalingMode.Fant>.  
  
 Если требуется более высокая точность, необходимо создать новую поверхность, когда контейнер <xref:System.Windows.Interop.D3DImage> изменяет размер.  
  
 Существует три способа обработки изменения размера.  
  
-   Участвовать в системе макета и создайте новую поверхность при изменении размера. Не создавайте слишком много поверхностей, поскольку может занимать и фрагментации памяти.  
  
-   Подождите, пока не произошло событие изменения размера для определенного периода времени, чтобы создать новую поверхность.  
  
-   Создание <xref:System.Windows.Threading.DispatcherTimer> , проверять размеры контейнера несколько раз в секунду.  
  
## <a name="multi-monitor-optimization"></a>Оптимизация нескольких мониторов  
 Значительное снижение производительности может произойти при перемещении система отрисовки <xref:System.Windows.Interop.D3DImage> на другой монитор.  
  
 В WDDM пока мониторы работают на одной видео карте и используется `Direct3DCreate9Ex`, нет без снижения производительности. Если мониторы используют разные видео карты, то производительность снижается. В Windows XP производительность снижается всегда.  
  
 Когда <xref:System.Windows.Interop.D3DImage> перемещается на другой монитор, можно создать новую поверхность на соответствующем адаптере, чтобы восстановить хорошую производительность.  
  
 Чтобы избежать снижения производительности, напишите код, специально для случая нескольких мониторов. Следующий список показывает один из способов написания кода для нескольких мониторов.  
  
1.  Найти точку <xref:System.Windows.Interop.D3DImage> в пространстве экрана с `Visual.ProjectToScreen` метод.  
  
2.  Используйте `MonitorFromPoint` метод GDI, чтобы найти монитор, отображающий эту точку.  
  
3.  Используйте `IDirect3D9::GetAdapterMonitor` метод, чтобы найти адаптер Direct3D9 монитор включен.  
  
4.  Если адаптер не является таким же, как адаптер с заднего буфера, создайте новый задний буфер для нового монитора и назначьте его <xref:System.Windows.Interop.D3DImage> заднего буфера.  
  
> [!NOTE]
>  Если <xref:System.Windows.Interop.D3DImage> распределяется между несколькими мониторами, производительность будет снижена, за исключением использования WDDM и `IDirect3D9Ex` на одном адаптере. Нет возможности для повышения производительности в этой ситуации.  
  
 В следующем примере кода показано, как найти текущего монитора.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 Обновление монитора при <xref:System.Windows.Interop.D3DImage> изменения размера или положения контейнера или обновите монитор с помощью `DispatcherTimer` , обновляющий несколько раз в секунду.  
  
## <a name="wpf-software-rendering"></a>Программная отрисовка WPF  
 WPF выполняет визуализацию синхронно в потоке пользовательского интерфейса в программном обеспечении в следующих ситуациях.  
  
-   Печать  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 При возникновении одной из этих ситуаций система отрисовки вызывает <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> для копирования в буфер оборудования для программного обеспечения. Реализация по умолчанию вызывает `GetRenderTargetData` метод с вашей рабочей областью. Так как этот вызов происходит вне шаблона блокирования и разблокирования, он может завершиться ошибкой. В этом случае `CopyBackBuffer` возвращает метод `null` и изображение не отображается.  
  
 Можно переопределить <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> метод, вызвать базовую реализацию, и если он возвращает `null`, может возвращать заполнитель <xref:System.Windows.Media.Imaging.BitmapSource>.  
  
 Также можно реализовать собственную программную отрисовку, вместо того чтобы вызывать базовую реализацию.  
  
> [!NOTE]
>  Если WPF выполняет отрисовку полностью в программном обеспечении <xref:System.Windows.Interop.D3DImage> не отображаются, так как WPF не имеет переднего буфера.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.D3DImage>  
 [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)  
 [Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)  
 [Пошаговое руководство. Размещение содержимого Direct3D9 в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
