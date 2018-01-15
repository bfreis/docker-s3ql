# docker-s3ql

Docker image with S3QL and Midnight Commander.

Build with:

    docker build -t bfreis/s3ql .

Use with:

    docker run \
      --rm -it \
      --cap-add sys_admin \
      --device=/dev/fuse \
      -v /MY_HOME_FOLDER:/MY_HOME_FOLDER \
      bfreis/s3ql \
      bash -c 'echo -ne "MY_S3_ACCESS_KEY\nMY_S3_SECRET_KEY\nMY_S3QL_FS_KEY\n" | mount.s3ql --allow-other s3://MY_BUCKET/MY_PREFIX/ /mnt/ && mc /mnt /MY_HOME_FOLDER && umount.s3ql /mnt'
  
  Replace `MY_HOME_FOLDER`, `MY_S3_ACCESS_KEY`, `MY_S3_SECRET_KEY`, `MY_S3QL_FS_KEY`, `MY_BUCKET`, and `MY_PREFIX` with appropriate values
  
