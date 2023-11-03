[back to index](../README.md)

# Matplotlib

The python matplotlib seems to be inspired by matlab, there are many similarities.

The main differences are, that most things work on the matplotlib.pyplot class instance,
whereas matlab uses mainly functions.

Also, the plot needs as the last command pyplot.show() to present anything to the user.

## Basic plots

```
import matplotlib.pyplot as plt

plt.subplot(121)
plt.plot(x, y, 'r+')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.title('Time Domain')
plt.xlim(0, 10)
plt.show()
```



[back to index](../README.md)
