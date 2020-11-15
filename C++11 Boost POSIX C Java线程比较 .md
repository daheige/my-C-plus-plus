# ������ļ򵥱Ƚ�

��Ȼ��C++11�ſ�ʼ��ʽ֧�ֲ����������߼�������Զ�֧�ֲ����Ͷ��߳��Ѿ�����ʲô�������ˡ�
���磬Java�ڵ�һ�������汾�о�֧�ֶ��̱߳��
��ĳЩƽ̨��Ҳ�ṩ����POSIX C��׼�Ķ��߳̽ӿڣ�����[Erlang](http://www.erlang.org/)֧����Ϣ��ͬ������(�е�������MPI)��
��Ȼ����ʹ��C++��Ŀ⣬����Boost���佫�ײ���߳̽ӿڽ��а�װ���������κθ�����ƽ̨(������ʹ��POSIX C�Ľӿڣ��������ӿ�)�����֧�ֵ�ƽ̨���ṩ����ֲ�ӿڡ�

��Щ����߱�����ԣ��Ѿ�д�˺ܶ���߳�Ӧ�ã�������ʹ����Щ��д���̴߳���ľ��飬���Խ����C++��
�����Java��POSIX C��ʹ��Boost�߳̿��C++���Լ�C++11�еĶ��̹߳��߽��м򵥵ıȽϣ���ȻҲ�ύ�����ñ��������½ڡ�

<table border=1>
  <td> ���� </td>
  <td> �����߳� </td>
  <td> ������ </td>
  <td> ����/�ȴ�ν�� </td>
  <td> ԭ�Ӳ����Ͳ�����֪�ڴ�ģ�� </td>
  <td> �̰߳�ȫ���� </td>
  <td> Futures(����) </td>
  <td> �̳߳� </td>
  <td> �߳��ж� </td>
<tr>
  <td>�½�����</td>
  <td>��2��</td>
  <td>��3��</td>
  <td>��4��</td>
  <td>��5��</td>
  <td>��6�º͵�7��</td>
  <td>��4��</td>
  <td>��9��</td>
  <td>��9��</td>
</tr>
<tr>
  <td rowspan=3> C++11 </td>
  <td rowspan=3> std::thread�����Ա���� </td>
  <td> std::mutex������Ա���� </td>
  <td> std::condition_variable </td>
  <td> std::atomic_xxx���� </td>
  <td rowspan=3> N/A </td>
  <td> std::future<> </td>
  <td rowspan=3> N/A </td>
  <td rowspan=3> N/A </td>
</tr>
<tr>
  <td> std::lock_guard<>ģ�� </td>
  <td rowspan=2> std::condition_variable_any������Ա���� </td>
  <td> std::atomic<>��ģ�� </td>
  <td> std::shared_future<> </td>
</tr>
<tr>
  <td> std::unique_lock<>ģ�� </td>
  <td> std::atomic_thread_fence()���� </td>
  <td> std::atomic_future<>��ģ�� </td>
</tr>
<tr>
  <td rowspan=3> Boost�߳̿� </td>
  <td rowspan=3> boost::thread��ͳ�Ա���� </td>
  <td> boost::mutex������Ա���� </td>
  <td> boost::condition_variable������Ա���� </td>
  <td rowspan=3> N/A </td>
  <td rowspan=3> N/A </td>
  <td> boost::unique_future<>��ģ��</td>
  <td rowspan=3> N/A </td>
  <td rowspan=3> boost::thread���interrupt()��Ա����</td>
</tr>
<tr>
  <td> boost::lock_guard<>��ģ�� </td>
  <td rowspan=2> boost::condition_variable_any������Ա���� </td>
  <td rowspan=2> boost::shared_future<>��ģ��</td>
</tr>
<tr>
  <td> boost::unique_lock<>��ģ�� </td>
</tr>
<tr>
  <td rowspan=4> POSIX C </td>
  <td> pthread_t������ص�API���� </td>
  <td> pthread_mutex_t������ص�API����</td>
  <td> pthread_cond_t������ص�API����</td>
  <td rowspan=4> N/A </td>
  <td rowspan=4> N/A </td>
  <td rowspan=4> N/A </td>
  <td rowspan=4> N/A </td>
  <td rowspan=4> pthread_cancel() </td>
</tr>
<tr>
  <td> pthread_create() </td>
  <td> pthread_mutex_lock() </td>
  <td> pthread_cond_wait() </td>
</tr>
<tr>
  <td> pthread_detach() </td>
  <td> pthread_mutex_unlock() </td>
  <td> pthread_cond_timed_wait() </td>
</tr>
<tr>
  <td> pthread_join() </td>
  <td> �ȵ� </td>
  <td> �ȵ� </td>
</tr>
<tr>
  <td> Java </td>
  <td> java.lang.thread�� </td>
  <td> synchronized�� </td>
  <td> java.lang.Object���wait()��notify()�����������ڲ�synchronized���� </td>
  <td> java.util.concurrent.atomic���е�volatile���ͱ��� </td>
  <td> java.util.concurrent���е����� </td>
  <td> ��java.util.concurrent.future�ӿ���ص��� </td>
  <td> java.util.concurrent.ThreadPoolExecutor�� </td>
  <td> java.lang.Thread���interrupt()���� </td>
</tr>
</table>
