<!-- eslint-disable vue/multi-word-component-names -->
// eslint-disable-next-line vue/multi-word-component-names
<template>
    <div>
      <video ref="videoElement" autoplay></video>
      <button @click="startRecording" v-if="!recording">Start Recording</button>
      <button @click="stopRecording" v-if="recording">Stop Recording</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CAMERA',
    data() {
      return {
        stream: null,
        recording: false,
        chunks: [],
      };
    },
    mounted() {
      this.setupCamera();
    },
    methods: {
      async setupCamera() {
        try {
          this.stream = await navigator.mediaDevices.getUserMedia({ video: true });
          this.$refs.videoElement.srcObject = this.stream;
        } catch (error) {
          console.error('Error accessing camera:', error);
        }
      },
      startRecording() {
        this.recording = true;
        this.chunks = [];
        const mediaRecorder = new MediaRecorder(this.stream);
        mediaRecorder.addEventListener('dataavailable', (event) => {
          if (event.data.size > 0) {
            this.chunks.push(event.data);
          }
        });
        mediaRecorder.addEventListener('stop', () => {
          const blob = new Blob(this.chunks, { type: 'video/webm' });
          const videoUrl = URL.createObjectURL(blob);
          
          console.log('Video URL:', videoUrl);
        });
        mediaRecorder.start();
      },
      stopRecording() {
        this.recording = false;
        this.stream.getTracks().forEach((track) => track.stop());
        this.stream = null;
      },
    },
  };
  </script>
  