import numpy as np
import matplotlib.pyplot as plt
import pywt
import pywt.data
original=pywt.data.camera()
title=['appoximation','horizontal details','vertical details','diagonal details']
coeffs2=pywt.dwt2(original,'bior1.3')
LL,(LH,LH,HL,HH)=coeffs2
fig=plt.figure(figsize=(12,3))
fori,a in enumerate([LL,LH,HL,HH]):
ax=fig.add_subplot(1,4,i+1)
ax.imshow(a,interpolation="nearest",cmap=plt.cm.gray)
ax.set_title(titles[i],fontsize=10)
ax.set_xticks([])
ax.set_yticks([])
fig.tight_layout90
plt.show()
