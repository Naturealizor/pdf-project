<!-- MixerDocs.svelte -->
<script lang="ts">
    let selectedDoc = $state('k5a');
  
    const documents = {
      k5a: {
        title: 'K5A/K5SS/KSM5/KM50/KSMC50',
        content: [
          'All K5A/K5SS models are of the same family and use all of the same internal components.',
          'The main difference between the models are the trim packages associated with each.',
          'Some models may have an overload reset, and some may be rated for commercial use.'
        ]
      },
      pro600: {
        title: 'Professional 600/Pro 5+/Professional HD',
        content: [
          'All of the above models are of the same family and use all of the same internal components.',
          'Over the years there have been a few variations of parts, but the overall design is identical.',
          'These units are designed for Professional Bowl Lift Models.'
        ]
      },
      pro6000hd: {
        title: 'Professional 6000HD, Proline 7Qt, and 8Qt Commercial',
        content: [
          'All of the DC powered models are of the same family and use all of the same internal components.',
          'The main difference between the models are the trim packages.',
          'The 6000HD has the tulip bowl, and the 8qt is rated for commercial use.'
        ]
      },
      tilthead: {
        title: 'Tilt Head Models',
        content: [
          'All tilt head models use the same internal components.',
          'Includes Artisan, Classic, UltraPower, Classic Plus, and Deluxe models.',
          'Main differences are bowl sizes and aesthetic features like handles.'
        ]
      },
      beater: {
        title: 'Beater Blade Guide',
        content: [
          'Beater Blade was the first paddle with a proprietary soft plastic edge.',
          'Features a powder coated metal frame and high quality soft plastic edges.',
          'Designed with a helical contour for optimal bowl contact.'
        ]
      },
      serial: {
        title: 'Serial Number Guide',
        content: [
          'Serial numbers contain manufacturing location, year, week, and unit number.',
          'Year codes recycle every 30 years.',
          'Week codes range from 00-52, starting with first Monday of the year.'
        ]
      }
    };
  </script>
  
  <div class="w-full max-w-4xl mx-auto p-4">
    <div class="bg-white rounded-lg shadow-lg">
      <div class="p-6 border-b border-gray-200">
        <h1 class="text-2xl font-bold">KitchenAid Mixer Documentation</h1>
      </div>
      
      <div class="flex flex-col md:flex-row gap-4 p-6">
        <!-- Navigation -->
        <nav class="w-full md:w-64 space-y-2">
          {#each Object.entries(documents) as [key, doc]}
            <button
              onclick={() => selectedDoc = key}
              class="w-full text-left px-4 py-2 rounded-lg transition-colors
                {selectedDoc === key 
                  ? 'bg-blue-100 text-blue-700' 
                  : 'hover:bg-gray-100'}"
            >
              {doc.title}
            </button>
          {/each}
        </nav>
  
        <!-- Content -->
        <div class="flex-1 p-4 bg-gray-50 rounded-lg">
          <h2 class="text-xl font-semibold mb-4">
            {documents[selectedDoc as keyof typeof documents].title}
          </h2>
          <div class="space-y-4">
            {#each documents[selectedDoc as keyof typeof documents].content as paragraph}
              <p class="text-gray-700">{paragraph}</p>
            {/each}
          </div>
        </div>
      </div>
    </div>
  </div>
  
  <style>
    /* Any additional component-specific styles can go here */
  </style>