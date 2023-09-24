<p align="center"> <img width="default" height="220"
        src="https://cdn.discordapp.com/attachments/736359303744585821/1155330120010182666/image.png">
</p>

# tween - C++ Tweening Library

`tween` is a library for interpolating numbers in C++. `tween` is great for applications such as games and ones with animations.

## Features

- Different easing styles (linear and sine)
- Timing is done internally, no extra code required
- Simple and easy interface

## Example

```cpp
#include <iostream>
#include <tween.hpp> // Path to

int main() {
	// Variables for the tween
	float initial = 0.f; // Starting value
	float target = 1.f; // Ending value
	int duration = 1000; // In milliseconds
	tween::easing easing_mode = tween::easing::sine_ease_in_out; // Easing mode

  	tween t(initial, target, duration, easing_mode);

	// Step at 60 frames per second
	while (true) {
		float value = t.step(); // Step the tween
		std::cout << value << std::endl;
		if (value == target) break;
		std::this_thread::sleep_for(std::chrono::milliseconds(1000 / 60));
	}
}
```
