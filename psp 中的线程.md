#
```
ֱ��ָ���صذ汾 ��ģ��Ҳһ����������
git clone https://gitee.com/wu_hong_chuan/ppsspp.git --recursive -b v1.9.4

```

#
```
tag 1.2.1
ext/natvie/threadĿ¼����
thread.h
���ͷ�ļ���ʵ����c++��׼�������thread

#define THREAD_HANDLE HANDLE
#define THREAD_HANDLE pthread_t
typedef THREAD_HANDLE native_handle_type;
native_handle_type m_handle;

	template <typename F>
	void StartThread(F* param)
	{
#ifdef USE_BEGINTHREADEX
		m_handle = (HANDLE)_beginthreadex(NULL, 0, &RunAndDelete<F>, param, 0, &m_id.m_thread);
#elif defined(_WIN32)
		m_handle = CreateThread(NULL, 0, &RunAndDelete<F>, param, 0, &m_id.m_thread);
#else
		pthread_attr_t attr;
		pthread_attr_init(&attr);
		pthread_attr_setstacksize(&attr, 1024 * 1024);
		if (pthread_create(&m_id.m_thread, &attr, &RunAndDelete<F>, param))
			m_id = id();
#endif
	}
	
	���Կ�����ͬƽ̨�����̵߳ľ���ʵ��
	����ʹ��c11������̣߳�������ǿ�ƽ̨��
```

```
tag 1.7.0 ִ��cmakeʱ�ᱨ��
��Ҫ��cmake/Toolchains/ios.cmake 35�����
set(CMAKE_XCODE_ATTRIBUTE_CODE_SIGN_IDENTITY?"")
```

```
����ֵ��һ��

threadpool
prioritizedworkqueue
threadutil ��װ��һ��event��	ʹ��std::condition_variable������condition_variable��wait��wait_for��notify_one����
executor
```

```
1.4.1֮���threadֱ������c++��׼���е�
1.2.1 base/mutex.h����event�Ŀ�ƽ̨��װ
```

```
1.2.1 
1.2.2
1.3
�����汾����ٷ��Ĺ���
ppsspp/ios����readme.md������xcode���̵�˵��
mkdir build-ios
cd build-ios
cmake -DCMAKE_TOOLCHAIN_FILE=../ios/ios.toolchain.cmake -GXcode ..

cmake ��������Ŀ¼bin����

ע�⣺�����������Ǵ�1.4.1�Ĺ��̱ȶԳ�����
����property with 'retain(or strong)' attribute must be of object type
1��natvie������̵�����
Build Settings/Deployment/IOS DeploymentTarget�ĳ� ios6.0
Build Settings/Apple Clang - Custom Compiler Flags/Other C Flags��Other C++ Flags ��� -mios-version-min=6.0

2�����̵�������ȥ�� -march=armv7-a
Build Settings/Apple Clang - Custom Compiler Flags/Other C Flags��Other C++ Flags

3��ע�͵����벻ͨ���Ļ�����
4��thread.h�ڴ�ע�͵���ʹ��c++��׼��� #inlude <thread>
5��u32 --> (u32)(long)
6��RemoteISOScreen.h 
���#include <thread>
ע�͵�
namespace std{
	class thread;
}
7��fast_math.cע�͵� fast_matrix_mul_4x4 = &fast_matrix_mul_4x4_neon(���Ӵ���û�н�fast_math_neon.S�������)
fast_matrix_mul_4x4_neon��arm���ʵ�ֵ�neon����
1.4�Ĺ����ǿ��Ա���.S�ļ�����ô����xCode�����ࣿ����

8��The clang compiler does not support '-mcpu=cortex-a9'
ȥ��-mfpu=cortex-a9
```