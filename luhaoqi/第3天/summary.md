1 ��������
	rt_pin_get()	��ȡ���ű��
	rt_pin_mode()	��������ģʽ//ͨ��ʹ��rt_pin_mode()�趨LED���ӵ�����Ϊ���ģʽ��Ȼ����ͨ��rt_pin_write()������д1����0�ķ�ʽ�Ϳ���ʹLED����˸
	rt_pin_write()	�������ŵ�ƽ
	rt_pin_read()	��ȡ���ŵ�ƽ
	rt_pin_attach_irq()	�������жϻص�����
	rt_pin_irq_enable()	ʹ�������ж�
	rt_pin_detach_irq()	���������жϻص�����

2 I2CͨѶЭ��
	���Ƚ���������Ӳ���п���ʹ��I2C�����齨�й�ѡI2C�豸����
	������ɺ����ص�������ͨ��list_deviceָ��鿴ϵͳ�豸��������I2C�豸�Ƿ�������

3 AHT10����������
	3.1������´�����г�ʼ��
	#include "sensor_asair_aht10.h"
	#define AHT10_I2C_BUS  "i2c1"

	int rt_hw_aht10_port(void)
	{
		struct rt_sensor_config cfg;

		cfg.intf.dev_name  = AHT10_I2C_BUS;
		cfg.intf.user_data = (void *)AHT10_I2C_ADDR;

		rt_hw_aht10_init("aht10", &cfg);

		return RT_EOK;
	}
	INIT_ENV_EXPORT(rt_hw_aht10_port);
	3.2ʹ��sensor probe temp_aht10����sensor probe humi_aht10������ѡ���¶Ȼ���ʪ��
	3.3ʹ��sensor read����ȡ��ֵ