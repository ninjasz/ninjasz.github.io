20211207  
# MT8735支持I2S音频输入  
android版本：8.0，I2S音频输出模块作为主，安卓模块做从。  
由于源码本身支持FM I2S输入，所以在FM基础上只做几个改动，就实现了本功能。  
1./kernel-3.18/sound/soc/mediatek/mt6735/mt_soc_pcm_fm_i2s.c  
m2ndI2SInAttribute.mI2S_IN_PAD_SEL = true;  
2.支持蓝牙播放得修改这个文件：/kernel-3.18/sound/soc/mediatek/mt6735/mt_soc_pcm_fm_i2s_awb.c  
m2ndI2SInAttribute.mI2S_IN_PAD_SEL = true;  
3./vendor/mediatek/kernel_modules/connectivity/fmradio/core/fm_config.c  
cfg->aud_cfg.i2s_info.mode = FM_I2S_SLAVE;  
cfg->aud_cfg.i2s_pad = FM_I2S_PAD_IO;