FROM arm32v7/alpine
EXPOSE 11000
COPY ./cloud-torrent /ct/
RUN chmod +x /ct/cloud-torrent
VOLUME [ "/downloads" ]
ENTRYPOINT ["/ct/cloud-torrent"]
