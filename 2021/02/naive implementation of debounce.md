function debounce(fn, delay) {
  let timer;
  return (...agrs) => {
    clearTimeout(timer);
    timer = setTimeout(() => {
      fn(...args);
    }, delay)
  }
}
