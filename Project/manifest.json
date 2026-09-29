self.addEventListener('install', (e) => {
  e.waitUntil(
    caches.open('personal-app-v1').then((cache) => {
      return cache.addAll([
        'index.html',
        'manifest.json'
        // Add your CSS or JS files here too if you have separate ones
      ]);
    })
  );
});

self.addEventListener('fetch', (e) => {
  e.respondWith(
    caches.match(e.request).then((response) => {
      return response || fetch(e.request);
    })
  );
});
